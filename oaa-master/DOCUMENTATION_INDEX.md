# Open Angel Arena 文档索引

本文档提供 OAA 项目所有文档的完整导航索引。

---

## 📖 快速导航

| 文档 | 说明 | 适合人群 |
|------|------|---------|
| [项目主文档 (中文)](README_CN.md) | 完整的项目介绍和概览 | 所有人 |
| [项目主文档 (英文)](README.md) | 原始英文文档 | 所有人 |
| [根目录文件说明](ROOT_FILES_GUIDE.md) | 根目录文件和配置说明 | 开发者 |

---

## 📁 目录结构文档

### 核心目录

| 目录 | 文档链接 | 说明 |
|------|---------|------|
| `game/` | [DIRECTORY_GUIDE.md](game/DIRECTORY_GUIDE.md) | 游戏运行时文件 |
| `content/` | [DIRECTORY_GUIDE.md](content/DIRECTORY_GUIDE.md) | 游戏资源源文件 |
| `docs/` | [DIRECTORY_GUIDE.md](docs/DIRECTORY_GUIDE.md) | 项目文档 |

### 脚本目录

| 目录 | 文档链接 | 说明 |
|------|---------|------|
| `game/scripts/vscripts/` | [DIRECTORY_GUIDE.md](game/scripts/vscripts/DIRECTORY_GUIDE.md) | Lua 游戏逻辑 |
| `game/scripts/npc/` | [DIRECTORY_GUIDE.md](game/scripts/npc/DIRECTORY_GUIDE.md) | NPC 数据定义 (KV) |
| `game/scripts/vscripts/components/` | [DIRECTORY_GUIDE.md](game/scripts/vscripts/components/DIRECTORY_GUIDE.md) | 游戏系统组件 |
| `game/scripts/npc/items/` | [DIRECTORY_GUIDE.md](game/scripts/npc/items/DIRECTORY_GUIDE.md) | 物品 KV 定义 |

---

## 🗂️ 文档结构图

```
oaa-master/
├── README.md                    # 项目主文档 (英文)
├── README_CN.md                 # 项目主文档 (中文) ⭐
├── ROOT_FILES_GUIDE.md          # 根目录文件说明
├── DOCUMENTATION_INDEX.md       # 本文档 - 文档索引
│
├── content/
│   └── DIRECTORY_GUIDE.md       # Content 目录说明
│
├── docs/
│   ├── README.md                # 官方文档入口
│   └── DIRECTORY_GUIDE.md       # Docs 目录说明
│
└── game/
    ├── DIRECTORY_GUIDE.md       # Game 目录说明
    │
    └── scripts/
        ├── npc/
        │   ├── DIRECTORY_GUIDE.md    # NPC 目录说明
        │   ├── Readme.md             # 原始说明
        │   │
        │   └── items/
        │       └── DIRECTORY_GUIDE.md # Items 目录说明
        │
        └── vscripts/
            ├── DIRECTORY_GUIDE.md    # VScripts 目录说明
            │
            └── components/
                └── DIRECTORY_GUIDE.md # Components 目录说明
```

---

## 📚 按主题索引

### 🎮 游戏系统

| 系统 | 相关文档 |
|------|---------|
| 英雄系统 | [NPC 目录](game/scripts/npc/DIRECTORY_GUIDE.md) > heroes/ |
| 技能系统 | [NPC 目录](game/scripts/npc/DIRECTORY_GUIDE.md) > abilities/ |
| 物品系统 | [Items 目录](game/scripts/npc/items/DIRECTORY_GUIDE.md) |
| 单位系统 | [NPC 目录](game/scripts/npc/DIRECTORY_GUIDE.md) > units/ |
| 组件系统 | [Components 目录](game/scripts/vscripts/components/DIRECTORY_GUIDE.md) |

### 🛠️ 开发相关

| 主题 | 相关文档 |
|------|---------|
| Lua 脚本 | [VScripts 目录](game/scripts/vscripts/DIRECTORY_GUIDE.md) |
| KV 文件 | [NPC 目录](game/scripts/npc/DIRECTORY_GUIDE.md) |
| UI 界面 | [Content 目录](content/DIRECTORY_GUIDE.md) > panorama/ |
| 粒子特效 | [Content 目录](content/DIRECTORY_GUIDE.md) > particles/ |
| 地图 | [Content 目录](content/DIRECTORY_GUIDE.md) > maps/ |

### 📋 配置文件

| 文件 | 位置 | 说明 |
|------|------|------|
| `addoninfo.txt` | `game/` | 游戏模式配置 |
| `herolist.txt` | `game/scripts/npc/` | 可选英雄列表 |
| `*_shops.txt` | `game/scripts/shops/` | 商店配置 |
| `addon_*.txt` | `game/resource/` | 本地化文件 |

---

## 🔍 常见任务导航

### 添加新内容

| 任务 | 需要修改的文件/目录 |
|------|-------------------|
| 添加新英雄 | `npc/heroes/`, `npc/abilities/`, `vscripts/abilities/`, `herolist.txt` |
| 添加新技能 | `npc/abilities/`, `vscripts/abilities/` |
| 添加新物品 | `npc/items/`, `vscripts/items/`, `shops/` |
| 添加新单位 | `npc/units/`, `vscripts/units/` |
| 添加新 UI | `content/panorama/` |
| 添加新粒子 | `content/particles/` |
| 添加新翻译 | `game/resource/addon_*.txt` |

### 修改游戏机制

| 任务 | 需要查看的文档 |
|------|---------------|
| 修改决斗系统 | [Components](game/scripts/vscripts/components/DIRECTORY_GUIDE.md) > duels/ |
| 修改金币系统 | [Components](game/scripts/vscripts/components/DIRECTORY_GUIDE.md) > gold/ |
| 修改经验系统 | [Components](game/scripts/vscripts/components/DIRECTORY_GUIDE.md) > experience/ |
| 修改 Boss 系统 | [Components](game/scripts/vscripts/components/DIRECTORY_GUIDE.md) > boss/ |

---

## 📝 文档编写规范

所有 `DIRECTORY_GUIDE.md` 文件遵循统一的格式：

1. **标题**：目录名称 + "结构说明"
2. **目录结构概览**：ASCII 树形图
3. **文件/目录说明**：表格形式
4. **开发指南**：如何添加新内容
5. **相关文档**：链接到其他相关文档

---

## 🔗 外部资源

- [GitHub 仓库](https://github.com/OpenAngelArena/oaa)
- [Discord 社区](https://discord.gg/WNFBB4d)
- [Valve Developer Wiki](https://developer.valvesoftware.com/wiki/Dota_2_Workshop_Tools)
- [ModDota 社区](https://moddota.com/)

---

## 📊 文档统计

| 类型 | 数量 |
|------|------|
| 目录说明文档 | 8 |
| 主要 README | 2 |
| 其他说明文档 | 2 |
| **总计** | **12** |

---

## 🆘 需要帮助？

1. **新手入门**：从 [README_CN.md](README_CN.md) 开始
2. **环境搭建**：查看 [docs/setup/](docs/setup/)
3. **具体开发**：根据任务类型查看对应目录的 `DIRECTORY_GUIDE.md`
4. **问题反馈**：提交 [GitHub Issue](https://github.com/OpenAngelArena/oaa/issues)
5. **社区交流**：加入 [Discord](https://discord.gg/WNFBB4d)

---

*本索引文档帮助您快速定位 Open Angel Arena 项目的各类文档*

*最后更新：2024年*
