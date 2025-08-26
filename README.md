# rust-taskmaster
I create a re-useable and portable taskmaster and basic rust dev tool for any new projects.

I've created a comprehensive system for copying this TaskMaster setup to

  我创建了一个完整的 Rust 专用 TaskMaster 开发包(也可以用于其他类型项目)，包含以下功能：

  🎉 已创建的包内容

  📦 打包文件

  - 目录: rust-taskmaster-package/
  - 压缩包: rust-taskmaster-package-20250826_111606.tar.gz

  🦀 Rust 特定优化

  - rskiller 缓存管理: 每 2 小时自动清理
  - 非交互式清理: 无需手动确认的安全清理模式
  - 优化的 Cargo 配置: 快速开发构建 + 生产优化
  - 自动化调度: macOS (launchd) 和 Linux (cron) 支持

  🤖 TaskMaster 集成

  - 完整的 Claude Code 和 Cursor MCP 配置
  - Rust 专用自定义命令
  - 项目管理和任务生成
  - 复杂度分析和任务扩展

  📝 使用方法

  快速部署:
  # 解压到新项目
  tar -xzf rust-taskmaster-package-20250826_111606.tar.gz
  cp -r rust-taskmaster-package/* your-new-rust-project/
  cd your-new-rust-project/

  # 运行一键设置
  ./setup-new-rust-project.sh "项目名称" "项目描述"

  ✨ 自动化功能

  - ✅ 每 2 小时自动缓存清理
  - ✅ 优化的构建配置
  - ✅ Claude Code 自定义命令
  - ✅ 开发工作流脚本
  - ✅ 完整文档和模板

  现在你有了一个可重复使用的 Rust
  开发环境包，可以轻松部署到任何新项目中！🚀
