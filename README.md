# Rust TaskMaster Tools

A comprehensive toolkit for Rust projects using TaskMaster AI for project management and development automation.

## Overview

This repository provides reusable tools and configurations for setting up TaskMaster AI in Rust projects, along with automated cache management and development workflow optimization.

## Features

### 🔧 Development Tools
- **Automated Rust Cache Management**: `rskiller` integration with scheduled cleanup every 2 hours
- **Development Environment Setup**: Automated tool configuration and dependencies
- **Template System**: Ready-to-use Rust project templates with TaskMaster integration

### 📋 TaskMaster Integration
- **Project Setup**: One-command initialization for TaskMaster in Rust projects
- **Documentation Templates**: Comprehensive guides for setup and usage
- **Configuration Management**: Pre-configured settings for optimal Rust development

### 🚀 Automation Scripts
- **Cache Management**: `scripts/rust-clean.sh` - Intelligent Rust cache cleaning
- **Environment Setup**: `scripts/setup-rust-automation.sh` - Complete development environment
- **Template Packaging**: `scripts/package-rust-template.sh` - Package tools for reuse

## Quick Start

### Option 1: Use as Git Submodule (Recommended)
```bash
# 1. Add this repo as a submodule to your Rust project
git submodule add https://github.com/jhfnetboy/rust-taskmaster.git tools/rust-taskmaster

# 2. Initialize the submodule
git submodule update --init --recursive

# 3. Copy tools to your project (optional, tools can be used directly from submodule)
cp tools/rust-taskmaster/scripts/* scripts/
cp tools/rust-taskmaster/templates/* templates/
```

### Option 2: Direct Copy
```bash
# 1. Clone the repository
git clone https://github.com/jhfnetboy/rust-taskmaster.git temp-rust-tools

# 2. Copy tools to your project
mkdir -p scripts templates docs
cp temp-rust-tools/scripts/* scripts/
cp temp-rust-tools/templates/* templates/
cp temp-rust-tools/docs/* docs/

# 3. Clean up
rm -rf temp-rust-tools
```

## Setup Instructions

### Step 1: Install Rust Cache Management (Optional but Recommended)
```bash
# This sets up rskiller and automated cache cleaning every 2 hours
chmod +x scripts/setup-rust-automation.sh
./scripts/setup-rust-automation.sh
```

### Step 2: Initialize TaskMaster AI
```bash
# Install TaskMaster AI globally
npm install -g task-master-ai

# Initialize in your Rust project
task-master init

# Or initialize with research capabilities
task-master init --research
```

### Step 3: Create Your First Tasks
```bash
# Method 1: From PRD document
echo "Build a Rust CLI tool with argument parsing" > docs/prd.txt
task-master parse-prd docs/prd.txt

# Method 2: Add tasks manually
task-master add-task --prompt="Setup Cargo project structure"
task-master add-task --prompt="Implement main CLI functionality"
task-master add-task --prompt="Add tests and documentation"
```

## Daily Usage

### Working with Tasks
```bash
# See all tasks
task-master list

# Get next task to work on
task-master next

# Start working on a task
task-master set-status --id=1.1 --status=in-progress

# Complete a task
task-master set-status --id=1.1 --status=done

# Get task details
task-master show 1.2
```

### Cache Management
```bash
# Manual cache cleanup (if you installed the automation)
./scripts/rust-clean.sh

# Check if automation is running
# macOS:
launchctl list | grep rust-clean
# Linux:
crontab -l | grep rust-clean
```

## Directory Structure

```
rust-taskmaster/
├── scripts/
│   ├── rust-clean.sh              # Cache management with rskiller
│   ├── setup-rust-automation.sh   # Complete environment setup
│   └── package-rust-template.sh   # Template packaging tool
├── templates/
│   └── rust-project-template.md   # Rust project template for TaskMaster
├── docs/
│   ├── Rust-Cache-Management.md   # Cache management documentation
│   ├── TaskMaster-Setup-Guide.md  # Complete setup guide
│   └── Quick-Setup-Commands.md    # Quick reference commands
└── README.md                      # This file
```
