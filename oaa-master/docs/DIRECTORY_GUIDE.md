# Docs 目录结构说明

本目录包含 Open Angel Arena 项目的所有文档资源，为开发者和贡献者提供完整的指南和参考资料。

---

## 📁 目录结构概览

```
docs/
├── .images/                # 文档使用的图片资源
├── balance/               # 游戏平衡性文档
├── bug-reports/           # Bug 报告指南
├── d2am/                  # Dota 2 Addon Manager 文档
├── design/                # 游戏设计文档
├── discord/               # Discord 社区指南
├── documentation/         # 文档编写指南
├── dota2tools/            # Dota 2 Workshop Tools 教程
├── git/                   # Git 版本控制指南
├── icons/                 # 图标制作指南
├── kv/                    # KeyValues 文件教程
├── lua/                   # Lua 脚本教程
├── map/                   # 地图编辑教程
├── materials/             # 材质制作教程
├── models/                # 模型制作教程
├── panorama/              # Panorama UI 教程
├── particles/             # 粒子特效教程
├── setup/                 # 项目安装配置指南
├── sound/                 # 音效制作教程
├── tourney/               # 锦标赛/比赛相关文档
├── translation/           # 翻译指南
├── writing/               # 文案编写指南
├── README.md              # 文档主入口
└── release.md             # 发布说明
```

---

## 📄 根目录文件

### `README.md`

**文档主入口**

项目文档的索引页面，包含所有文档的链接和简要说明。新贡献者应首先阅读此文件。

### `release.md`

**发布说明**

记录版本发布历史、更新日志和变更说明。

---

## 📁 目录详解

### .images/ - 文档图片资源

存放文档中使用的截图、示意图和其他图片资源。

---

### balance/ - 平衡性文档

游戏平衡性相关的文档，包括：

- 英雄平衡调整记录
- 物品平衡数据
- 数值设计理念
- 平衡性讨论和决策记录

**目标读者**：游戏设计师、平衡性测试人员

---

### bug-reports/ - Bug 报告指南

指导用户和测试人员如何正确报告 Bug：

- Bug 报告模板
- 问题分类标准
- 复现步骤编写指南
- 日志收集方法

**目标读者**：测试人员、玩家

---

### d2am/ - Dota 2 Addon Manager 文档

[Dota 2 Addon Manager](https://github.com/chrisinajar/dota2-addon-manager) 使用指南：

- 安装配置说明
- 项目链接方法
- 常见问题解答
- 多项目管理

**目标读者**：开发者

---

### design/ - 游戏设计文档

游戏设计理念和规划：

- 核心玩法设计
- 系统设计文档
- 新功能规划
- 设计决策记录

**目标读者**：游戏设计师、项目负责人

---

### discord/ - Discord 社区指南

OAA Discord 服务器相关信息：

- 服务器规则
- 频道说明
- 角色和权限
- 社区行为准则

**目标读者**：社区成员

---

### documentation/ - 文档编写指南

如何为项目编写和维护文档：

- 文档风格指南
- Markdown 格式规范
- 文档更新流程
- 模板和示例

**目标读者**：文档贡献者

---

### dota2tools/ - Dota 2 Workshop Tools 教程

Valve 官方开发工具使用指南：

- Workshop Tools 安装
- 工具概览和功能
- 常用操作流程
- 调试技巧

**目标读者**：新手开发者

---

### git/ - Git 版本控制指南

Git 和 GitHub 使用教程：

- Git 基础命令
- 分支管理策略
- Pull Request 流程
- 代码审查指南
- 冲突解决方法

**目标读者**：所有贡献者

---

### icons/ - 图标制作指南

游戏图标（技能图标、物品图标等）制作教程：

- 图标尺寸规范
- 风格指南
- 制作工具推荐
- 导出格式要求

**目标读者**：美术设计师

---

### kv/ - KeyValues 文件教程

Dota 2 KV 文件格式详解：

- KV 语法基础
- 技能定义教程
- 物品定义教程
- 单位定义教程
- 英雄定义教程
- 常见错误和解决方案

**目标读者**：游戏程序员、设计师

---

### lua/ - Lua 脚本教程

Dota 2 Lua API 使用指南：

- Lua 语言基础
- Dota 2 API 参考
- 技能脚本编写
- 物品脚本编写
- 修改器（Modifier）编写
- 调试技巧
- 最佳实践

**目标读者**：游戏程序员

---

### map/ - 地图编辑教程

Hammer Editor 地图编辑指南：

- Hammer 基础操作
- 实体放置
- 触发器设置
- 地形编辑
- 光照设置
- 编译和测试

**目标读者**：地图设计师

---

### materials/ - 材质制作教程

材质和纹理制作指南：

- 材质系统概述
- VMAT 文件格式
- 纹理制作规范
- PBR 材质工作流
- 材质编辑器使用

**目标读者**：美术设计师

---

### models/ - 模型制作教程

3D 模型制作和导入指南：

- 模型规格要求
- Blender/Maya 工作流
- 骨骼和动画
- 模型导入流程
- LOD 设置

**目标读者**：3D 美术师

---

### panorama/ - Panorama UI 教程

Dota 2 Panorama UI 框架教程：

- Panorama 架构概述
- XML 布局编写
- CSS 样式设计
- JavaScript 脚本
- 与 Lua 交互
- 自定义 HUD 元素

**目标读者**：UI 开发者

---

### particles/ - 粒子特效教程

粒子特效制作指南：

- Particle Editor 使用
- 发射器类型
- 操作器和渲染器
- 特效优化
- 常用特效技巧

**目标读者**：特效美术师

---

### setup/ - 项目安装配置指南

项目开发环境搭建：

- **install.md** - 安装说明
- 环境配置要求
- 依赖项安装
- 首次运行指南
- 常见问题解答

**目标读者**：新手开发者

**重要文件**：这是新贡献者最先需要阅读的文档之一。

---

### sound/ - 音效制作教程

音效和音乐制作指南：

- 音频格式要求
- Sound Event 编写
- 音效导入流程
- 音量和混音规范

**目标读者**：音效设计师

---

### tourney/ - 锦标赛文档

OAA 比赛和锦标赛相关：

- 比赛规则
- 赛事组织指南
- 积分系统说明
- 观战模式配置

**目标读者**：赛事组织者、玩家

---

### translation/ - 翻译指南

多语言翻译贡献指南：

- 翻译文件格式
- 翻译流程
- 术语表
- 风格指南
- 语言优先级

**支持语言**：英语、中文、俄语、德语、西班牙语、葡萄牙语、波兰语、匈牙利语、荷兰语、捷克语

**目标读者**：翻译贡献者

---

### writing/ - 文案编写指南

游戏内文案和故事编写：

- 写作风格指南
- 英雄背景故事
- 技能描述规范
- 物品描述规范
- 语调和用词

**目标读者**：文案作者

---

## 🚀 快速入门推荐阅读顺序

### 新手开发者

1. `setup/install.md` - 环境搭建
2. `git/` - 版本控制
3. `dota2tools/` - 工具使用
4. `kv/` - KV 文件基础
5. `lua/` - Lua 脚本

### 美术贡献者

1. `setup/install.md` - 环境搭建
2. `icons/` - 图标制作
3. `models/` - 模型制作
4. `particles/` - 粒子特效
5. `materials/` - 材质制作

### 翻译贡献者

1. `translation/` - 翻译指南
2. `git/` - 提交翻译
3. `documentation/` - 文档规范

### 游戏设计师

1. `design/` - 设计文档
2. `balance/` - 平衡性
3. `kv/` - 数值配置
4. `writing/` - 文案编写

---

## 📚 相关文档

- [项目主文档](../README_CN.md)
- [Game 目录详解](../game/DIRECTORY_GUIDE.md)
- [Content 目录详解](../content/DIRECTORY_GUIDE.md)
- [VScripts 目录详解](../game/scripts/vscripts/DIRECTORY_GUIDE.md)
- [NPC 目录详解](../game/scripts/npc/DIRECTORY_GUIDE.md)

---

## 🔗 外部资源

- [Dota 2 Workshop Tools Wiki](https://developer.valvesoftware.com/wiki/Dota_2_Workshop_Tools)
- [Lua API 文档](https://developer.valvesoftware.com/wiki/Dota_2_Workshop_Tools/Scripting/API)
- [ModDota 社区](https://moddota.com/)
- [GitHub 仓库](https://github.com/OpenAngelArena/oaa)
- [Discord 服务器](https://discord.gg/WNFBB4d)

---

## 📝 贡献文档

如果您发现文档中有错误或遗漏，欢迎提交 Pull Request 进行改进：

1. Fork 本仓库
2. 编辑相关文档
3. 提交 Pull Request
4. 等待审核合并

请遵循 `documentation/` 目录中的编写规范。

---

*本文档用于说明 Open Angel Arena 的 docs 目录结构*
