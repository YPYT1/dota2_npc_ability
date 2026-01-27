# OAA 根目录文件说明

本文档说明 Open Angel Arena 项目根目录下各个文件和隐藏目录的用途。

---

## 📁 隐藏目录

### `.circleci/`

**CircleCI 持续集成配置**

包含 CircleCI CI/CD 流水线配置文件，用于自动化测试和部署。

- 代码提交后自动触发构建
- 运行 Lua 代码检查
- 执行自动化测试
- 构建状态徽章显示

---

## 📄 配置文件

### `.all-contributorsrc`

**All Contributors 配置**

[All Contributors](https://github.com/kentcdodds/all-contributors) 规范的配置文件，用于管理项目贡献者列表。

```json
{
  "projectName": "oaa",
  "projectOwner": "OpenAngelArena",
  "contributors": [...]
}
```

---

### `.editorconfig`

**编辑器配置**

统一不同编辑器/IDE 的代码风格设置：

- 缩进风格（空格/制表符）
- 缩进大小
- 文件编码（UTF-8）
- 行尾符号
- 文件末尾空行

支持的编辑器：VS Code、Sublime Text、Vim、Atom 等

---

### `.gitignore`

**Git 忽略文件配置**

定义哪些文件/目录不应被 Git 版本控制追踪：

- 编译生成的文件
- IDE 配置文件
- 操作系统临时文件
- 依赖目录（node_modules）
- 本地配置文件

---

### `.luacheckrc`

**Luacheck 代码检查配置**

Lua 静态代码分析工具配置：

- 代码规范检查
- 潜在错误检测
- 全局变量白名单
- 忽略规则配置

**使用方法**：
```bash
luacheck game/scripts/vscripts/
```

---

### `.nvmrc`

**Node.js 版本配置**

指定项目使用的 Node.js 版本，供 NVM (Node Version Manager) 使用：

```
14
```

**使用方法**：
```bash
nvm use
```

---

## 📄 文档文件

### `README.md`

**项目主说明文档（英文）**

项目的主要介绍文档，包含：

- 项目简介
- 快速开始指南
- 贡献者指南
- 贡献者列表
- 许可证信息

---

### `README_CN.md`

**项目主说明文档（中文）**

详细的中文文档，包含：

- 游戏介绍
- 游戏特色
- 项目结构
- 安装指南
- 开发指南
- 多语言支持

---

### `AGENTS.md`

**AI Agent 配置说明**

为 AI 助手（如 GitHub Copilot、Claude 等）提供的项目上下文说明文件。

---

## 📄 依赖管理文件

### `package.json`

**Node.js 项目配置**

定义 Node.js 项目的元数据和依赖：

```json
{
  "name": "oaa",
  "version": "1.0.0",
  "scripts": {
    "lint": "luacheck game/scripts/vscripts/"
  },
  "dependencies": {...},
  "devDependencies": {...}
}
```

**常用命令**：
```bash
npm install    # 安装依赖
npm run lint   # 运行代码检查
```

---

### `package-lock.json`

**NPM 依赖锁定文件**

精确锁定所有依赖的版本号，确保不同环境下安装的依赖版本一致。

> ⚠️ 此文件由 npm 自动生成，不要手动编辑

---

### `yarn.lock`

**Yarn 依赖锁定文件**

Yarn 包管理器的依赖锁定文件，功能类似 `package-lock.json`。

> ⚠️ 此文件由 yarn 自动生成，不要手动编辑

---

## 📄 工具脚本

### `git-fix-whitespace`

**Git 空白字符修复脚本**

修复代码中的空白字符问题：

- 行尾多余空格
- 文件末尾空行
- 制表符/空格混用

**使用方法**：
```bash
./git-fix-whitespace
```

---

## 📁 主要目录

| 目录 | 说明 | 详细文档 |
|------|------|---------|
| `content/` | 游戏资源源文件 | [查看](content/DIRECTORY_GUIDE.md) |
| `contrib/` | 贡献者工具和脚本 | - |
| `docs/` | 项目文档 | [查看](docs/DIRECTORY_GUIDE.md) |
| `game/` | 游戏运行时文件 | [查看](game/DIRECTORY_GUIDE.md) |
| `libs/` | 外部依赖库 | - |
| `scripts/` | 构建和工具脚本 | - |
| `workshop/` | Steam 创意工坊资源 | - |

---

## 📁 libs/ 目录

**外部依赖库**

包含项目依赖的外部库文件：

| 文件 | 说明 |
|------|------|
| `libmpg123-0.dll` | MP3 音频解码库（Windows） |

---

## 📁 contrib/ 目录

**贡献者工具**

为贡献者提供的辅助工具和脚本。

---

## 📁 scripts/ 目录

**构建脚本**

项目构建、打包和部署相关的脚本。

---

## 📁 workshop/ 目录

**Steam 创意工坊**

Steam 创意工坊上传相关的资源和配置。

---

## 🔧 开发环境设置

### 推荐工具

1. **代码编辑器**：VS Code + Lua 扩展
2. **版本控制**：Git
3. **Node.js**：用于运行构建脚本
4. **Dota 2 Workshop Tools**：游戏开发工具

### 首次设置

```bash
# 1. 克隆仓库
git clone https://github.com/OpenAngelArena/oaa.git

# 2. 安装 Node.js 依赖
npm install

# 3. 使用正确的 Node.js 版本
nvm use

# 4. 运行代码检查
npm run lint
```

---

## 📚 相关文档

- [Game 目录详解](game/DIRECTORY_GUIDE.md)
- [Content 目录详解](content/DIRECTORY_GUIDE.md)
- [Docs 目录详解](docs/DIRECTORY_GUIDE.md)
- [VScripts 目录详解](game/scripts/vscripts/DIRECTORY_GUIDE.md)
- [NPC 目录详解](game/scripts/npc/DIRECTORY_GUIDE.md)
- [Components 目录详解](game/scripts/vscripts/components/DIRECTORY_GUIDE.md)

---

*本文档用于说明 Open Angel Arena 根目录下的文件和目录*
