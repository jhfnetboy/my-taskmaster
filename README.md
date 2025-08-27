# My-TaskMaster: Multi-Stack Development Automation Toolkit
V 0.2 now.

# My-TaskMaster: 多技术栈开发自动化工具包

A comprehensive development toolkit for multi-stack projects with TaskMaster AI integration, featuring automatic tech stack detection and smart tooling for Rust, Node.js, Frontend (TypeScript), Golang, Solidity, and Python projects.

一个综合的多技术栈项目开发工具包，集成 TaskMaster AI，具有自动技术栈检测功能，智能支持 Rust、Node.js、前端 (TypeScript)、Golang、Solidity 和 Python 项目。

---

## ✨ Key Features / 主要功能

### 🔍 **Smart Tech Stack Detection / 智能技术栈检测**
- Automatically detects project technology stacks / 自动检测项目技术栈
- Supports: Rust, Node.js, Frontend (TypeScript/JavaScript), Golang, Solidity, Python / 支持：Rust、Node.js、前端 (TypeScript/JavaScript)、Golang、Solidity、Python
- Conditional tool installation based on detected stacks / 根据检测到的技术栈有条件安装工具

### 🔧 **Stack-Specific Automation / 技术栈特定自动化**
- **Rust**: `rskiller` cache management with 2-hour scheduled cleanup / **Rust**: 使用 `rskiller` 缓存管理，每2小时自动清理
- **Node.js/Frontend**: `pnpm` package management with optimization / **Node.js/前端**: 使用 `pnpm` 包管理和优化
- **Golang**: Code formatting and linting with `gofumpt` and `golangci-lint` / **Golang**: 使用 `gofumpt` 和 `golangci-lint` 进行代码格式化和代码检查
- **Solidity**: Foundry/Forge development with Anvil local blockchain / **Solidity**: 使用 Foundry/Forge 开发，集成 Anvil 本地区块链
- **Python**: Code quality with `black`, `flake8`, and `mypy` / **Python**: 使用 `black`、`flake8` 和 `mypy` 进行代码质量管理

### 📋 **TaskMaster AI Integration / TaskMaster AI 集成**
- One-command project initialization / 一键项目初始化
- Multi-language project templates / 多语言项目模板
- AI-powered task management and complexity analysis / AI 驱动的任务管理和复杂性分析

### 🚀 **Universal Development Commands / 通用开发命令**
- Cross-stack cleaning and optimization / 跨技术栈清理和优化
- Unified build and test workflows / 统一构建和测试流程
- Custom Claude Code slash commands / 自定义 Claude Code 斜杠命令

---

## 🚀 Quick Start / 快速开始

**任何新的多技术栈项目都可以通过以下方式使用这套工具，我会持续更新，添加常规开发功能，例如文档体系等等：**

### Option 1: Use as Git Submodule (Recommended) / 选项1：作为 Git 子模块使用（推荐）

```bash
# Add this repo as a submodule to your project
# 将此仓库作为子模块添加到你的项目中
git submodule add https://github.com/jhfnetboy/rust-taskmaster.git tools/my-taskmaster

# Initialize the submodule
# 初始化子模块
git submodule update --init --recursive

# Run smart setup (detects your tech stack automatically)
# 运行智能设置（自动检测你的技术栈）
chmod +x tools/my-taskmaster/scripts/setup-smart-automation.sh
./tools/my-taskmaster/scripts/setup-smart-automation.sh
```

### Option 2: Direct Installation / 选项2：直接安装

```bash
# Clone the repository
# 克隆仓库
git clone https://github.com/jhfnetboy/rust-taskmaster.git temp-my-taskmaster

# Copy tools to your project
# 将工具复制到你的项目中
mkdir -p scripts templates docs
cp -r temp-my-taskmaster/scripts/* scripts/
cp -r temp-my-taskmaster/templates/* templates/
cp -r temp-my-taskmaster/docs/* docs/

# Run setup
# 运行设置
chmod +x scripts/setup-smart-automation.sh
./scripts/setup-smart-automation.sh

# Clean up
# 清理
rm -rf temp-my-taskmaster
```

### Quick Reference for Legacy Rust Projects / Rust 项目快速参考

```bash
# 简化的快速设置（保持向后兼容）
# Simplified quick setup (maintaining backward compatibility)

# 添加工具包作为子模块
git submodule add https://github.com/jhfnetboy/rust-taskmaster.git tools/rust-taskmaster

# 复制工具到项目
cp tools/rust-taskmaster/scripts/* scripts/
cp tools/rust-taskmaster/templates/* templates/

# 设置自动化环境
chmod +x scripts/setup-rust-automation.sh
./scripts/setup-rust-automation.sh

# 初始化TaskMaster
npm install -g task-master-ai
task-master init
```

---

## 🔍 Tech Stack Detection / 技术栈检测

The toolkit automatically detects your project's technology stacks and installs appropriate tools:

工具包会自动检测你项目的技术栈并安装相应的工具：

### Supported Stacks / 支持的技术栈

| Stack | Detection Method | Tools Installed | 技术栈 | 检测方法 | 安装的工具 |
|-------|------------------|-----------------|--------|----------|------------|
| **Rust** | `Cargo.toml` exists | `rskiller` (cache management) | **Rust** | 存在 `Cargo.toml` | `rskiller`（缓存管理） |
| **Node.js Backend** | `package.json` (no frontend frameworks) | `pnpm`, `nodemon`, `npm-check-updates` | **Node.js 后端** | `package.json`（无前端框架） | `pnpm`、`nodemon`、`npm-check-updates` |
| **Frontend** | `package.json` with React/Vue/Angular/etc. | `pnpm`, `typescript`, `npm-check-updates` | **前端** | 包含 React/Vue/Angular 等的 `package.json` | `pnpm`、`typescript`、`npm-check-updates` |
| **Golang** | `go.mod` or `go.sum` exists | `gofumpt`, `golangci-lint` | **Golang** | 存在 `go.mod` 或 `go.sum` | `gofumpt`、`golangci-lint` |
| **Solidity** | `foundry.toml` or Hardhat config | `foundry`, `forge`, `anvil`, `solhint` | **Solidity** | `foundry.toml` 或 Hardhat 配置 | `foundry`、`forge`、`anvil`、`solhint` |
| **Python** | `requirements.txt`, `pyproject.toml`, `setup.py` | `black`, `flake8`, `mypy` | **Python** | `requirements.txt`、`pyproject.toml`、`setup.py` | `black`、`flake8`、`mypy` |

### Manual Detection / 手动检测

```bash
# Check what tech stacks are detected in your project
# 检查在你的项目中检测到了哪些技术栈
./scripts/detect-tech-stack.sh

# Auto-install tools for detected stacks
# 为检测到的技术栈自动安装工具
./scripts/detect-tech-stack.sh --setup
```

---

## 📖 Setup Instructions / 设置说明

### Prerequisites / 先决条件

Make sure you have the required tools installed for your tech stack:

确保已为你的技术栈安装了必要的工具：

```bash
# For any stack / 对于任何技术栈
node.js >= 16.0.0    # For TaskMaster AI / 用于 TaskMaster AI

# For Rust projects / 对于 Rust 项目
rustc >= 1.70.0

# For Node.js/Frontend projects / 对于 Node.js/前端项目  
npm >= 8.0.0         # Will install pnpm automatically / 会自动安装 pnpm
pnpm >= 7.0.0        # Preferred package manager / 首选包管理器

# For Golang projects / 对于 Golang 项目
go >= 1.19

# For Python projects / 对于 Python 项目
python >= 3.8
```

### Step-by-Step Setup / 分步设置

#### Step 1: Install TaskMaster AI / 第1步：安装 TaskMaster AI

```bash
# Install globally
# 全局安装
npm install -g task-master-ai

# Verify installation
# 验证安装
task-master --version
```

#### Step 2: Initialize Your Project / 第2步：初始化你的项目

```bash
# Run smart automation setup (this will detect your tech stack)
# 运行智能自动化设置（这将检测你的技术栈）
./scripts/setup-smart-automation.sh

# This will:
# 这将会：
# 1. Detect your project's tech stacks
# 1. 检测你项目的技术栈
# 2. Install appropriate development tools
# 2. 安装适当的开发工具
# 3. Configure TaskMaster AI
# 3. 配置 TaskMaster AI
# 4. Set up automated maintenance
# 4. 设置自动维护
```

#### Step 3: Create Your First Tasks / 第3步：创建你的第一个任务

```bash
# Method 1: Use the project template
# 方法1：使用项目模板
# Edit the PRD template for your tech stack
# 为你的技术栈编辑 PRD 模板
nano .taskmaster/docs/prd.txt

# Generate tasks from PRD
# 从 PRD 生成任务
task-master parse-prd .taskmaster/docs/prd.txt --num-tasks=0

# Method 2: Add tasks manually
# 方法2：手动添加任务
task-master add-task --prompt="Set up project structure and dependencies"
task-master add-task --prompt="Implement core functionality"
task-master add-task --prompt="Add comprehensive tests"
task-master add-task --prompt="Set up CI/CD pipeline"
```

---

## 💻 Daily Usage / 日常使用

### Task Management / 任务管理

```bash
# See all tasks
# 查看所有任务
task-master list

# Get next task to work on  
# 获取下一个要处理的任务
task-master next

# Start working on a task
# 开始处理一个任务
task-master set-status --id=1.1 --status=in-progress

# Complete a task
# 完成一个任务
task-master set-status --id=1.1 --status=done

# Get detailed task information
# 获取详细的任务信息
task-master show 1.2
```

### Multi-Stack Operations / 多技术栈操作

```bash
# Clean all detected tech stacks
# 清理所有检测到的技术栈
./scripts/clean-multi-stack.sh --safe

# Check tech stack status
# 检查技术栈状态  
./scripts/detect-tech-stack.sh

# Optimize project for all stacks
# 为所有技术栈优化项目
./scripts/optimize-multi-stack.sh
```

### Claude Code Integration / Claude Code 集成

```bash
# Available slash commands in Claude Code:
# 在 Claude Code 中可用的斜杠命令：

/clean-project          # Clean artifacts for all detected stacks
                        # 清理所有检测到技术栈的构件

/optimize-project       # Optimize performance for all stacks  
                        # 为所有技术栈优化性能

/build-project          # Build and test all detected stacks
                        # 构建和测试所有检测到的技术栈

/detect-stacks          # Show detected tech stacks and tools
                        # 显示检测到的技术栈和工具
```

---

## 📁 Directory Structure / 目录结构

```
my-taskmaster/
├── scripts/
│   ├── detect-tech-stack.sh           # Smart tech stack detection
│   │                                   # 智能技术栈检测
│   ├── setup-smart-automation.sh      # Multi-stack environment setup
│   │                                   # 多技术栈环境设置
│   ├── setup-rust-automation.sh       # Rust-specific setup (legacy)
│   │                                   # Rust 特定设置（遗留）
│   ├── rust-clean.sh                  # Rust cache management
│   │                                   # Rust 缓存管理
│   ├── clean-multi-stack.sh           # Cross-stack cleaning
│   │                                   # 跨技术栈清理
│   └── package-rust-template.sh       # Template packaging tool
│                                       # 模板打包工具
├── templates/
│   ├── rust-project-template.md       # Rust project PRD template
│   │                                   # Rust 项目 PRD 模板
│   ├── nodejs-project-template.md     # Node.js project template
│   │                                   # Node.js 项目模板
│   ├── frontend-project-template.md   # Frontend project template
│   │                                   # 前端项目模板
│   └── golang-project-template.md     # Golang project template
│                                       # Golang 项目模板
├── docs/
│   ├── Multi-Stack-Setup-Guide.md     # Complete setup guide
│   │                                   # 完整设置指南
│   ├── Tech-Stack-Detection.md        # Detection system docs
│   │                                   # 检测系统文档
│   └── Quick-Setup-Commands.md        # Quick reference
│                                       # 快速参考
└── README.md                          # This file / 此文件
```

---

## 🔧 Advanced Configuration / 高级配置

### Customizing Tech Stack Detection / 自定义技术栈检测

You can modify the detection logic in `scripts/detect-tech-stack.sh`:

你可以在 `scripts/detect-tech-stack.sh` 中修改检测逻辑：

```bash
# Add custom detection for your framework
# 为你的框架添加自定义检测
if [[ -f "your-config-file.json" ]]; then
    stacks+=("your-custom-stack")
    echo -e "${GREEN}✅ Your Custom Stack detected${NC}"
fi
```

### Adding New Tech Stack Support / 添加新技术栈支持

1. **Update Detection Logic / 更新检测逻辑**: Edit `detect-tech-stack.sh` / 编辑 `detect-tech-stack.sh`
2. **Add Tools / 添加工具**: Update `get_tools_for_stack()` function / 更新 `get_tools_for_stack()` 函数
3. **Setup Commands / 设置命令**: Update `get_setup_commands()` function / 更新 `get_setup_commands()` 函数
4. **Automation / 自动化**: Add stack-specific logic in `setup-smart-automation.sh` / 在 `setup-smart-automation.sh` 中添加技术栈特定逻辑

---

## 🏗️ Automated Features / 自动化功能

### Cross-Platform Scheduling / 跨平台调度

The toolkit sets up automated maintenance based on your operating system:

工具包根据你的操作系统设置自动化维护：

#### macOS
- **launchd** service for automated cleaning / 用于自动清理的 **launchd** 服务
- Runs every 2 hours / 每2小时运行一次
- Logs to `~/.multi-stack-clean.log` / 记录到 `~/.multi-stack-clean.log`

#### Linux  
- **cron** job for automated cleaning / 用于自动清理的 **cron** 作业
- Runs every 2 hours / 每2小时运行一次
- Logs to `~/.multi-stack-clean.log` / 记录到 `~/.multi-stack-clean.log`

### Monitoring Automation / 监控自动化

```bash
# Check if automation is running
# 检查自动化是否正在运行

# macOS:
launchctl list | grep multi-stack

# Linux:
crontab -l | grep multi-stack

# View automation logs
# 查看自动化日志
tail -f ~/.multi-stack-clean.log
```

---

## 🐛 Troubleshooting / 故障排除

### Common Issues / 常见问题

#### 1. **TaskMaster not found / TaskMaster 未找到**
```bash
npm install -g task-master-ai
# Verify: / 验证：
task-master --version
```

#### 2. **Tech stack not detected / 技术栈未检测到**
```bash
# Check if you're in the right directory
# 检查你是否在正确的目录中
ls -la

# Run detection manually
# 手动运行检测
./scripts/detect-tech-stack.sh
```

#### 3. **Permission denied / 权限被拒绝**
```bash
# Make scripts executable
# 使脚本可执行
chmod +x scripts/*.sh
```

#### 4. **Automation not running / 自动化未运行**
```bash
# macOS: Reload launch agent
# macOS：重新加载启动代理
launchctl unload ~/Library/LaunchAgents/com.user.multi-stack-clean.plist
launchctl load ~/Library/LaunchAgents/com.user.multi-stack-clean.plist

# Linux: Check cron service
# Linux：检查 cron 服务
sudo systemctl status cron
```

### Validation Commands / 验证命令

```bash
# Check all installations
# 检查所有安装
./scripts/validate-setup.sh

# Test tech stack detection
# 测试技术栈检测
./scripts/detect-tech-stack.sh

# Verify TaskMaster configuration
# 验证 TaskMaster 配置
task-master models
task-master list
```

---

## 🤝 Contributing / 贡献

We welcome contributions! Here's how you can help:

我们欢迎贡献！以下是你可以帮助的方式：

1. **Add support for new tech stacks / 添加对新技术栈的支持**
2. **Improve detection algorithms / 改进检测算法**
3. **Add more automation features / 添加更多自动化功能**
4. **Improve documentation / 改进文档**
5. **Report bugs and issues / 报告错误和问题**

### Development Setup / 开发设置

```bash
# Fork and clone the repository
# Fork 并克隆仓库
git clone https://github.com/your-username/rust-taskmaster.git
cd rust-taskmaster

# Test your changes
# 测试你的更改
./scripts/detect-tech-stack.sh
./scripts/setup-smart-automation.sh
```

---

## 📝 License / 许可证

MIT License - see [LICENSE](LICENSE) file for details.

MIT 许可证 - 详情请参阅 [LICENSE](LICENSE) 文件。

---

## 🙏 Acknowledgments / 致谢

- **[TaskMaster AI](https://github.com/eyaltoledano/claude-task-master)** for project management capabilities / 项目管理功能
- **[rskiller](https://crates.io/crates/rskiller)** for Rust cache management / Rust 缓存管理  
- **Claude Code** for development workflow integration / 开发流程集成
- Community contributors and feedback / 社区贡献者和反馈

---

## 📞 Support / 支持

- **Issues**: [GitHub Issues](https://github.com/jhfnetboy/rust-taskmaster/issues)
- **Documentation**: Check the `docs/` folder / 查看 `docs/` 文件夹
- **Community**: Join our discussions / 加入我们的讨论

---

**Happy Multi-Stack Development! 🚀✨**
**祝你多技术栈开发愉快！🚀✨**
