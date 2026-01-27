# VScripts 目录结构说明

本目录包含 Open Angel Arena 的所有 Lua 游戏逻辑脚本，是游戏运行的核心代码库。

---

## 📁 目录结构概览

```
vscripts/
├── addon_game_mode.lua     # 游戏模式入口点
├── addon_init.lua          # 初始化脚本
├── gamemode.lua            # 游戏模式主逻辑
├── settings.lua            # 游戏设置配置
├── events.lua              # 游戏事件处理器
├── precache.lua            # 资源预加载定义
├── components.lua          # 组件加载器
├── linker.lua              # 模块链接器
├── abilities/              # 英雄技能 Lua 实现
├── bots/                   # Bot AI 脚本
├── components/             # 游戏系统组件
├── internal/               # 内部工具脚本
├── items/                  # 物品 Lua 实现
├── libraries/              # 公共工具库
├── modifiers/              # Buff/Debuff 修改器
├── statcollection/         # 统计数据收集
└── units/                  # 单位 AI 脚本
```

---

## 📄 根目录核心文件

### `addon_game_mode.lua`

**游戏模式入口点**

Dota 2 加载自定义游戏时首先调用的文件。负责：
- 初始化游戏模式
- 调用 `Precache()` 函数预加载资源
- 调用 `Activate()` 函数激活游戏模式

### `addon_init.lua`

**初始化脚本**

在游戏模式激活前执行的初始化逻辑。

### `gamemode.lua`

**游戏模式主逻辑**

定义 `GameMode` 类，包含：
- 游戏规则设置
- 游戏阶段控制
- 核心游戏逻辑

### `settings.lua`

**游戏设置配置**

包含游戏的各种配置常量：
- 游戏时间设置
- 金币/经验倍率
- 复活时间配置
- 决斗/Boss 相关设置

### `events.lua`

**游戏事件处理器**

处理所有游戏事件的回调函数：
- 英雄击杀事件
- 游戏状态变化
- 玩家连接/断开
- 物品购买/拾取

### `precache.lua`

**资源预加载定义**

定义需要预加载的游戏资源：
- 模型文件
- 粒子特效
- 音效文件
- 单位定义

### `components.lua`

**组件加载器**

负责加载 `components/` 目录下的所有游戏组件。

### `linker.lua`

**模块链接器**

处理 Lua 模块之间的依赖关系和链接。

---

## 📁 abilities/ - 技能脚本

英雄技能的 Lua 实现。

### 子目录

| 目录 | 说明 |
|------|------|
| `boss/` | Boss 技能脚本 |
| `bubble_witch/` | 泡泡女巫技能 |
| `electrician/` | 电工技能 |
| `eul/` | 尤尔技能 |
| `misc/` | 杂项技能 |
| `neutrals/` | 中立生物技能 |
| `sohei/` | 僧兵技能 |
| `tinkerer/` | 修补匠（重制）技能 |

### 核心文件

| 文件 | 说明 |
|------|------|
| `baseclass.lua` | 技能基类，提供通用功能 |
| `bot_controller.lua` | Bot 技能控制器 |
| `dev_attack.lua` | 开发测试用攻击技能 |
| `fountain_attack.lua` | 泉水攻击技能 |
| `tiny_grow.lua` | 小小成长技能 |
| `visage_gravekeepers_cloak.lua` | 维萨吉墓地斗篷 |

### 英雄技能文件 (oaa_*.lua)

以 `oaa_` 前缀命名的文件是 OAA 自定义或修改的技能：

| 文件 | 说明 |
|------|------|
| `oaa_abaddon_borrowed_time.lua` | 阿巴顿 - 回光返照 |
| `oaa_alchemist_chemical_rage.lua` | 炼金术士 - 化学狂暴 |
| `oaa_alchemist_greevils_greed.lua` | 炼金术士 - 贪魔的贪婪 |
| `oaa_arcane_orb.lua` | 神谕法球 |
| `oaa_bash_of_the_deep.lua` | 深海重击 |
| `oaa_bristleback.lua` | 钢背兽 - 刚毛后背 |
| `oaa_meepo_divided_we_stand.lua` | 米波 - 分则能立 |
| `oaa_rearm.lua` | 修补匠 - 再装填 |
| `oaa_wukongs_command.lua` | 齐天大圣 - 猴子猴孙 |
| ... | 更多英雄技能 |

---

## 📁 bots/ - Bot AI 脚本

Bot 玩家的 AI 逻辑实现。

---

## 📁 components/ - 游戏组件

游戏系统的模块化组件。每个组件负责一个独立的游戏系统。

### 组件列表

| 组件目录 | 说明 |
|---------|------|
| `abilities/` | 技能系统组件 |
| `boss/` | Boss 战斗系统 |
| `bottlepass/` | 瓶子通行证系统 |
| `capturepoints/` | 占领点系统 |
| `cave/` | 洞穴探索系统 |
| `corepoints/` | 核心积分系统 |
| `courier/` | 信使系统 |
| `creeps/` | 小兵系统 |
| `devcheats/` | 开发者作弊命令 |
| `doors/` | 门控制系统 |
| `duels/` | 决斗系统 |
| `experience/` | 经验系统 |
| `filters/` | 过滤器系统 |
| `glyph/` | 防御符文系统 |
| `gold/` | 金币系统 |
| `heroselection/` | 英雄选择系统 |
| `items/` | 物品系统 |
| `minimap/` | 小地图系统 |
| `music/` | 音乐系统 |
| `player/` | 玩家系统 |
| `points/` | 积分系统 |
| `progression/` | 进度系统 |
| `reflexfilters/` | 反射过滤器 |
| `runes/` | 符文系统 |
| `saveload/` | 存档/加载系统 |
| `sparks/` | 火花效果系统 |
| `startingitems/` | 初始物品系统 |
| `statprovider/` | 属性提供者 |
| `surrender/` | 投降系统 |
| `team_select/` | 队伍选择系统 |
| `zonecontrol/` | 区域控制系统 |

### 入口文件

| 文件 | 说明 |
|------|------|
| `index.lua` | 组件索引和加载器 |

---

## 📁 internal/ - 内部工具

内部使用的工具脚本和辅助函数。

---

## 📁 items/ - 物品脚本

物品的 Lua 实现。

### 子目录

| 目录 | 说明 |
|------|------|
| `farming/` | 打钱类物品 |
| `neutral/` | 中立物品 |
| `reflex/` | 反射类物品 |
| `transformation/` | 变身类物品 |

### 核心文件

| 文件 | 说明 |
|------|------|
| `baseclass.lua` | 物品基类 |

### 物品脚本示例

| 文件 | 说明 |
|------|------|
| `aeon_disk.lua` | 永恒之盘 |
| `aghanims.lua` | 阿哈利姆神杖 |
| `black_king_bar.lua` | 黑皇杖 |
| `bloodstone.lua` | 血精石 |
| `bottle.lua` | 魔瓶 |
| `butterfly.lua` | 蝴蝶 |
| `dagon.lua` | 达贡之神力 |
| `hand_of_midas.lua` | 迈达斯之手 |
| `refresher.lua` | 刷新球 |
| `angels_halo.lua` | 天使光环（自定义） |
| `bubble_orb.lua` | 泡泡法球（自定义） |
| `devastator.lua` | 毁灭者（自定义） |
| `ghost_king_bar.lua` | 幽灵黑皇杖（自定义） |
| `giant_form.lua` | 巨人形态（自定义） |
| `magic_lamp.lua` | 魔法神灯（自定义） |
| ... | 更多物品 |

---

## 📁 libraries/ - 公共库

可复用的工具函数和类库。

### 子目录

| 目录 | 说明 |
|------|------|
| `modifiers/` | 修改器相关库 |

### 库文件

| 文件 | 说明 |
|------|------|
| `abilities.lua` | 技能工具函数 |
| `animations.lua` | 动画工具函数 |
| `basehero.lua` | 英雄基类扩展 |
| `basenpc.lua` | NPC 基类扩展 |
| `buildings.lua` | 建筑物工具函数 |
| `cfinder.lua` | 单位查找工具 |
| `chatcommand.lua` | 聊天命令处理 |
| `event.lua` | 事件系统 |
| `fun.lua` | 通用工具函数 |
| `functional.lua` | 函数式编程工具 |
| `gamerules.lua` | 游戏规则扩展 |
| `math.lua` | 数学工具函数 |
| `notifications.lua` | 通知系统 |
| `playerresource.lua` | 玩家资源扩展 |
| `playertables.lua` | 玩家数据表 |
| `timers.lua` | 定时器系统 |
| `vector_targeting.lua` | 向量目标选择 |

---

## 📁 modifiers/ - 修改器

Buff/Debuff 修改器的 Lua 实现。

### 子目录

| 目录 | 说明 |
|------|------|
| `ardm/` | ARDM 模式修改器 |
| `funmodifiers/` | 趣味修改器 |
| `modifyabilitiesfilter/` | 技能修改过滤器 |
| `sparks/` | 火花特效修改器 |

### 基类文件

| 文件 | 说明 |
|------|------|
| `baseclass.lua` | 修改器基类 |
| `aura_baseclass.lua` | 光环修改器基类 |

### 修改器示例

| 文件 | 说明 |
|------|------|
| `modifier_anti_stun_oaa.lua` | 防眩晕修改器 |
| `modifier_boss_capture_point.lua` | Boss 占领点修改器 |
| `modifier_boss_phase_controller.lua` | Boss 阶段控制器 |
| `modifier_building_construction.lua` | 建筑建造修改器 |
| `modifier_creep_loot.lua` | 小兵掉落修改器 |
| `modifier_duel_invulnerability.lua` | 决斗无敌修改器 |
| `modifier_generic_bonus.lua` | 通用属性加成 |
| `modifier_generic_projectile.lua` | 通用弹道修改器 |
| `modifier_offside.lua` | 越位修改器 |
| `modifier_out_of_duel.lua` | 决斗区域外修改器 |
| `modifier_shrine_oaa.lua` | 圣坛修改器 |
| ... | 更多修改器 |

---

## 📁 statcollection/ - 统计收集

游戏统计数据收集模块，用于分析和改进游戏平衡。

---

## 📁 units/ - 单位 AI

单位 AI 脚本，控制非玩家单位的行为。

### AI 脚本列表

| 文件 | 说明 |
|------|------|
| `ai_alchemist.lua` | 炼金术士野怪 AI |
| `ai_baneling.lua` | 爆虫 AI |
| `ai_bear_boss.lua` | 熊王 Boss AI |
| `ai_carapace.lua` | 甲壳虫 AI |
| `ai_core_guy.lua` | 核心守卫 AI |
| `ai_dire_hound_boss.lua` | 夜魇猎犬 Boss AI |
| `ai_dire_tower_boss.lua` | 夜魇塔 Boss AI |
| `ai_grendel.lua` | 格伦德尔 AI |
| `ai_killer_tomato.lua` | 杀手番茄 AI |
| `ai_lycan_boss.lua` | 狼人 Boss AI |
| `ai_magma_boss.lua` | 岩浆 Boss AI |
| `ai_ogre_seer.lua` | 食人魔先知 AI |
| `ai_ogre_tank_boss.lua` | 食人魔坦克 Boss AI |
| `ai_poison_spider.lua` | 毒蜘蛛 AI |
| `ai_roshan.lua` | 肉山 AI |
| `ai_simple.lua` | 简单 AI 基类 |
| `ai_slime.lua` | 史莱姆 AI |
| `ai_slime_spawner.lua` | 史莱姆生成器 AI |
| `ai_spider_boss.lua` | 蜘蛛 Boss AI |
| `ai_spiders.lua` | 蜘蛛群 AI |
| `ai_spooky_ghost.lua` | 幽灵 AI |
| `ai_swiper.lua` | 横扫者 AI |
| `ai_temple_guardian.lua` | 神殿守卫 AI |
| `ai_tormentor_boss.lua` | 折磨者 Boss AI |
| `ai_wanderer.lua` | 流浪者 AI |
| `ai_werewolf.lua` | 狼人 AI |
| `charger.lua` | 冲锋者 AI |
| `shielder.lua` | 盾卫者 AI |
| `twin.lua` | 双子 AI |

---

## 🔧 开发指南

### 创建新技能

1. **创建 Lua 文件**
   ```lua
   -- abilities/my_hero_ability.lua
   my_hero_ability = class({})
   
   function my_hero_ability:OnSpellStart()
       -- 技能逻辑
   end
   ```

2. **继承基类**（可选）
   ```lua
   LinkLuaModifier("modifier_my_ability", "abilities/my_hero_ability", LUA_MODIFIER_MOTION_NONE)
   ```

3. **创建对应的 KV 定义**在 `scripts/npc/abilities/`

### 创建新物品

1. **创建 Lua 文件**
   ```lua
   -- items/my_item.lua
   item_my_item = class({})
   
   function item_my_item:OnSpellStart()
       -- 物品主动效果
   end
   
   function item_my_item:GetIntrinsicModifierName()
       return "modifier_item_my_item"
   end
   ```

2. **创建对应的 KV 定义**在 `scripts/npc/items/`

### 创建新修改器

```lua
-- modifiers/modifier_my_buff.lua
modifier_my_buff = class({})

function modifier_my_buff:IsHidden() return false end
function modifier_my_buff:IsPurgable() return true end
function modifier_my_buff:IsDebuff() return false end

function modifier_my_buff:DeclareFunctions()
    return {
        MODIFIER_PROPERTY_ATTACKSPEED_BONUS_CONSTANT,
    }
end

function modifier_my_buff:GetModifierAttackSpeedBonus_Constant()
    return 50
end
```

### 创建新组件

1. 在 `components/` 下创建新目录
2. 创建 `init.lua` 作为入口
3. 在 `components/index.lua` 中注册

---

## 📚 相关文档

- [NPC 目录详解](../npc/DIRECTORY_GUIDE.md)
- [Game 目录详解](../../DIRECTORY_GUIDE.md)
- [Lua API 文档](https://developer.valvesoftware.com/wiki/Dota_2_Workshop_Tools/Scripting/API)
- [项目主文档](../../../README_CN.md)

---

*本文档用于说明 Open Angel Arena 的 vscripts 目录结构*
