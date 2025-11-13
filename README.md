# Dota 2 NPC 技能库

这是一个综合性的 Dota 2 自定义技能和法术库，整合了两个优秀的开源项目，为 Dota 2 MOD 开发者提供完整的技能实现参考和资源。

## 📦 项目内容

### dota-2-lua-abilities
完整的 Dota 2 自定义技能实现项目，包含：

#### 🎮 核心资源
- **997+ Lua 脚本文件** - 完整的技能逻辑实现
  - 自定义英雄技能（Aqua、Azura、Darkness、Maple、Megumin 等）
  - 原版英雄技能的 Lua 重制版本
  - 技能修改器（Modifier）系统
  - 技能特效和行为逻辑

#### 🎨 视觉资源
- **156+ 粒子特效文件** (.vpcf_c)
  - 技能释放特效
  - 持续效果粒子
  - 爆炸、投射物、光环等特效
  - 自定义英雄专属特效

#### 🖼️ UI 与界面
- **Panorama UI 系统**
  - 自定义技能界面布局
  - 技能图标和资源
  - 英雄选择界面
  - JavaScript 交互脚本

#### 🎭 模型与材质
- **3D 模型文件** (.vmdl_c, .vmesh_c)
  - Rubick 方块、蛋等自定义模型
  - 技能召唤物模型
- **材质贴图** (.vmat_c, .vtex_c)
  - 技能特效材质
  - 英雄皮肤材质
  - 粒子纹理

#### 🗺️ 地图与配置
- **地图文件** - hero_demo_main.vpk
- **NPC 数据配置**
  - 技能数据定义
  - 英雄属性配置
  - 单位数据
- **本地化文本** - 技能描述和界面文本

### SpellLibrary-master
Dota 2 MOD 社区维护的英雄技能重制库（1183 个文件）

#### 📚 内容特点
- 社区驱动的技能重制项目
- 标准化的代码规范和文档
- Datadriven 和 Lua 混合实现
- 完整的技能依赖说明

## 🚀 使用方法

### 安装步骤
1. 克隆或下载本仓库
```bash
git clone https://github.com/YPYT1/dota2_npc_ability.git
```

2. 将 `dota-2-lua-abilities` 文件夹复制到 Dota 2 插件目录
```
你的Dota2文件夹/game/dota_addons/
```

3. 启动 Dota 2，在控制台中运行
```
dota_launch_custom_game dota-2-lua-abilities（需要换成你自己的项目名称） dota（你自己的地图名称）
```

### 测试建议
- 建议开启作弊模式以便快速测试技能效果
- 使用 `-lvlup 25` 快速升级
- 使用 `-gold 99999` 获取金币购买装备
- 使用 `-refresh` 刷新技能冷却

## 📂 目录结构

```
dota-2-lua-abilities/
├── scripts/vscripts/          # Lua 脚本文件（997+ 文件）
│   ├── custom_abilities/      # 自定义技能实现
│   ├── addon_game_mode.lua    # 游戏模式主文件
│   └── addon_init.lua         # 初始化脚本
├── particles/                 # 粒子特效（156+ 文件）
├── materials/                 # 材质和贴图
├── models/                    # 3D 模型文件
├── panorama/                  # UI 界面
│   ├── images/               # 技能图标、英雄头像
│   ├── layout/               # 界面布局
│   ├── scripts/              # UI 脚本
│   └── styles/               # 样式表
├── maps/                      # 地图文件
└── resource/                  # 本地化和配置
    ├── addon_english.txt      # 英文文本
    └── flash3/images/         # 技能图标资源

SpellLibrary-master/
└── game/                      # 标准化的技能库
    ├── scripts/npc/           # NPC 和技能数据
    └── scripts/vscripts/      # Lua 脚本实现
```

## 🎯 技能分类

### 自定义英雄技能
- **Aqua** - 水系女神技能（复活、祝福、神圣驱散等）
- **Azura** - 暗影弓箭手技能（多重射击、暗影形态等）
- **Darkness** - 十字军战士技能（冲锋、诱饵、先锋等）
- **Maple** - 防御型英雄技能（吞噬、掩护移动、九头蛇等）
- **Megumin** - 爆炸魔法师技能
- **Fairy Queen** - 仙女女王技能（魅惑、精灵召唤等）
- **Midas** - 黄金系列技能（点金术、黄金爆发等）
- **Red Transistor** - 晶体管系列技能（多种科技风格技能）

### 原版英雄技能重制
包含大量原版 Dota 2 英雄技能的 Lua 实现版本，可用于学习和参考。

## 🛠️ 技术特点

- **纯 Lua 实现** - 所有技能逻辑使用 Lua 编写，易于修改和学习
- **模块化设计** - 每个技能独立封装，便于复用
- **完整的 Modifier 系统** - 包含 Buff、Debuff、光环等各类效果
- **自定义粒子特效** - 丰富的视觉效果实现
- **Panorama UI 集成** - 现代化的用户界面
- **详细注释** - 代码包含中英文注释，便于理解

## 📖 学习资源

本项目适合以下用途：
- 学习 Dota 2 技能开发
- 参考技能实现逻辑
- 复用现有技能代码
- 开发自定义游戏模式
- 研究粒子特效系统
- 学习 Panorama UI 开发

## 🤝 贡献与协作

本项目整合了社区的优秀资源，欢迎：
- 报告 Bug 和问题
- 提交新的技能实现
- 改进现有代码
- 完善文档和注释
- 分享使用经验

## 📜 版权说明

本项目整合了以下开源项目：
- **dota-2-lua-abilities** - 由 [elfansoer](https://github.com/elfansoer/dota-2-lua-abilities) 创建和维护
- **SpellLibrary** - 由 Dota 2 MOD 社区共同维护

各子项目遵循其原有的开源协议，详见各目录下的 LICENSE 文件。

## 🔗 相关链接

- [ModDota 社区](https://moddota.com/)
- [Dota 2 Workshop Tools Wiki](https://developer.valvesoftware.com/wiki/Dota_2_Workshop_Tools)
- [原始 dota-2-lua-abilities 项目](https://github.com/elfansoer/dota-2-lua-abilities)
- [原始 SpellLibrary 项目](https://github.com/Pizzalol/SpellLibrary)

## 💡 注意事项

- 部分技能实现可能与游戏内原版有细微差异，这是有意为之
- 随着项目规模扩大，无法保证所有技能完全无 Bug
- 本项目仅供学习和 MOD 开发使用
- 需要 Dota 2 Reborn 工具支持
- 详情内容请查看 [项目详细介绍文档](./introduce.md)
---

**统计数据：** 997+ Lua 脚本 | 156+ 粒子特效 | 2287 个文件 | 160,000+ 行代码
