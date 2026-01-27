# NPC 目录结构说明

本目录包含 Open Angel Arena 的所有 NPC 数据定义文件，使用 KeyValues (KV) 格式定义游戏中的英雄、技能、物品和单位。

---

## 📁 目录结构概览

```
npc/
├── abilities/              # 技能 KV 定义
│   ├── boss/              # Boss 技能
│   ├── items/             # 物品技能
│   ├── misc/              # 杂项技能
│   ├── neutrals/          # 中立生物技能
│   └── talents/           # 天赋技能
├── heroes/                 # 英雄 KV 定义
├── items/                  # 物品 KV 定义
│   ├── basic/             # 基础物品
│   ├── blinks/            # 闪烁类物品
│   ├── boss/              # Boss 掉落物品
│   ├── custom/            # 自定义物品
│   ├── dev/               # 开发测试物品
│   └── neutral/           # 中立物品
├── portraits/              # 英雄头像配置
├── units/                  # 单位 KV 定义
│   ├── boss/              # Boss 单位
│   ├── buildings/         # 建筑单位
│   ├── minimap/           # 小地图标记单位
│   ├── misc/              # 杂项单位
│   └── neutrals/          # 中立生物
├── herolist.txt            # 可选英雄白名单
├── herolist_*.txt          # 各模式英雄列表
├── neutral_items.txt       # 中立物品配置
├── npc_abilities_custom.txt    # 自定义技能入口
├── npc_abilities_override.txt  # 原版技能覆盖
├── npc_heroes_custom.txt       # 自定义英雄入口
├── npc_items_custom.txt        # 自定义物品入口
├── npc_units_custom.txt        # 自定义单位入口
├── portraits.txt           # 头像配置入口
└── Readme.md               # 原始说明文件
```

---

## 📄 根目录核心文件

### `herolist.txt`

**可选英雄白名单**

定义游戏中可选择的英雄列表。格式为：
```
"whitelist"
{
    "npc_dota_hero_abaddon"    "1"    // 1 = 启用, 0 = 禁用
    "npc_dota_hero_axe"        "1"
    ...
}
```

### 英雄列表变体

| 文件 | 说明 |
|------|------|
| `herolist.txt` | 默认英雄列表 |
| `herolist_10v10.txt` | 10v10 模式英雄列表 |
| `herolist_2_6_players.txt` | 2-6 玩家模式 |
| `herolist_ardm.txt` | ARDM 模式 |
| `herolist_blood_magic.txt` | 血魔法模式 |
| `herolist_cm.txt` | 队长模式 |
| `herolist_lp.txt` | 低优先级模式 |

### `npc_abilities_custom.txt`

**自定义技能入口文件**

使用 `#base` 指令引入所有技能定义文件。

### `npc_abilities_override.txt`

**原版技能覆盖**

修改 Dota 2 原版技能的属性值，用于平衡调整。

### `npc_heroes_custom.txt`

**自定义英雄入口文件**

使用 `#base` 指令引入所有英雄定义文件。

### `npc_items_custom.txt`

**自定义物品入口文件**

使用 `#base` 指令引入所有物品定义文件。

### `npc_units_custom.txt`

**自定义单位入口文件**

使用 `#base` 指令引入所有单位定义文件。

### `neutral_items.txt`

**中立物品配置**

定义中立物品的掉落等级和规则。

### `portraits.txt`

**头像配置**

定义英雄选择界面的头像显示。

---

## 📁 abilities/ - 技能定义

英雄技能的 KV 数据定义。

### 目录结构

| 目录 | 说明 |
|------|------|
| `boss/` | Boss 专属技能 |
| `items/` | 物品主动技能 |
| `misc/` | 杂项/通用技能 |
| `neutrals/` | 中立生物技能 |
| `talents/` | 英雄天赋定义 |

### 技能文件命名规则

- `{hero}_{ability}.txt` - 标准技能
- `{hero}_{ability}_oaa.txt` - OAA 修改/自定义版本

### 技能文件示例

| 文件 | 说明 |
|------|------|
| `abaddon_aphotic_shield.txt` | 阿巴顿 - 无光之盾 |
| `abaddon_borrowed_time_oaa.txt` | 阿巴顿 - 回光返照 (OAA版) |
| `axe_berserkers_call.txt` | 斧王 - 狂战士之吼 |
| `invoker_cold_snap.txt` | 祈求者 - 急速冷却 |
| `sohei_dash_oaa.txt` | 僧兵 - 冲刺 (自定义英雄) |
| `electrician_static_grip_oaa.txt` | 电工 - 静电束缚 (自定义英雄) |
| `bubble_witch_blow_bubbles_oaa.txt` | 泡泡女巫 - 吹泡泡 (自定义英雄) |

### 技能 KV 格式示例

```
"DOTAAbilities"
{
    "ability_name"
    {
        "BaseClass"             "ability_lua"
        "ScriptFile"            "abilities/ability_name.lua"
        "AbilityTextureName"    "ability_icon"
        "AbilityBehavior"       "DOTA_ABILITY_BEHAVIOR_UNIT_TARGET"
        "AbilityUnitTargetTeam" "DOTA_UNIT_TARGET_TEAM_ENEMY"
        "AbilityUnitTargetType" "DOTA_UNIT_TARGET_HERO | DOTA_UNIT_TARGET_BASIC"
        "SpellImmunityType"     "SPELL_IMMUNITY_ENEMIES_NO"
        "AbilityCastRange"      "600"
        "AbilityCastPoint"      "0.3"
        "AbilityCooldown"       "10"
        "AbilityManaCost"       "100"
        
        "AbilitySpecial"
        {
            "01"
            {
                "var_type"      "FIELD_INTEGER"
                "damage"        "100 150 200 250"
            }
        }
    }
}
```

---

## 📁 heroes/ - 英雄定义

所有英雄的 KV 数据定义。

### 核心文件

| 文件 | 说明 |
|------|------|
| `base.txt` | 英雄基础属性模板 |

### 英雄文件

每个英雄一个独立的 `.txt` 文件：

| 文件 | 英雄 |
|------|------|
| `abaddon.txt` | 阿巴顿 |
| `alchemist.txt` | 炼金术士 |
| `antimage.txt` | 敌法师 |
| `axe.txt` | 斧王 |
| `invoker.txt` | 祈求者 |
| `sohei.txt` | 僧兵 (自定义) |
| `electrician.txt` | 电工 (自定义) |
| `bubble_witch.txt` | 泡泡女巫 (自定义) |
| `eul.txt` | 尤尔 (自定义) |
| `largo.txt` | 拉戈 (自定义) |
| ... | 130+ 英雄 |

### 英雄 KV 格式示例

```
"DOTAHeroes"
{
    "npc_dota_hero_axe"
    {
        "override_hero"     "npc_dota_hero_axe"
        
        "AttributePrimary"  "DOTA_ATTRIBUTE_STRENGTH"
        "AttributeBaseStrength"     "25"
        "AttributeStrengthGain"     "3.4"
        "AttributeBaseIntelligence" "18"
        "AttributeIntelligenceGain" "1.6"
        "AttributeBaseAgility"      "20"
        "AttributeAgilityGain"      "2.2"
        
        "StatusHealth"      "200"
        "StatusMana"        "75"
        "MovementSpeed"     "310"
        "ArmorPhysical"     "0"
        "AttackDamageMin"   "27"
        "AttackDamageMax"   "31"
        "AttackRate"        "1.7"
        "AttackRange"       "150"
        
        "Ability1"  "axe_berserkers_call"
        "Ability2"  "axe_battle_hunger"
        "Ability3"  "axe_counter_helix"
        "Ability4"  "axe_culling_blade"
        ...
    }
}
```

---

## 📁 items/ - 物品定义

所有物品的 KV 数据定义。

### 目录结构

| 目录 | 说明 |
|------|------|
| `basic/` | 基础组件物品 |
| `blinks/` | 闪烁类物品 |
| `boss/` | Boss 掉落专属物品 |
| `custom/` | OAA 自定义物品 |
| `dev/` | 开发测试物品 |
| `neutral/` | 中立物品 |

### 物品升级系统

OAA 大部分物品支持升级，命名规则：
- `item_xxx.txt` - 1级物品
- `item_xxx_2.txt` - 2级物品
- `item_xxx_3.txt` - 3级物品
- `item_xxx_4.txt` - 4级物品
- `item_xxx_5.txt` - 5级物品

### 物品文件示例

| 文件 | 说明 |
|------|------|
| `item_abyssal_blade.txt` | 深渊之刃 1级 |
| `item_abyssal_blade_2.txt` | 深渊之刃 2级 |
| `item_abyssal_blade_5.txt` | 深渊之刃 5级 |
| `item_black_king_bar.txt` | 黑皇杖 |
| `item_butterfly.txt` | 蝴蝶 |
| `item_heart.txt` | 恐鳌之心 |
| `item_refresher.txt` | 刷新球 |
| `item_dagon.txt` | 达贡之神力 1级 |
| `item_dagon_9.txt` | 达贡之神力 9级 |

### 自定义物品

位于 `custom/` 目录：

| 文件 | 说明 |
|------|------|
| `item_angels_halo.txt` | 天使光环 |
| `item_bubble_orb.txt` | 泡泡法球 |
| `item_devastator.txt` | 毁灭者 |
| `item_ghost_king_bar.txt` | 幽灵黑皇杖 |
| `item_magic_lamp.txt` | 魔法神灯 |

### 物品 KV 格式示例

```
"DOTAAbilities"
{
    "item_example"
    {
        "BaseClass"             "item_lua"
        "ScriptFile"            "items/example.lua"
        "AbilityTextureName"    "item_example"
        "AbilityBehavior"       "DOTA_ABILITY_BEHAVIOR_IMMEDIATE | DOTA_ABILITY_BEHAVIOR_NO_TARGET"
        
        "ItemCost"              "5000"
        "ItemShopTags"          "damage;hard_to_tag"
        "ItemQuality"           "epic"
        "ItemAliases"           "example"
        "ItemDeclarations"      "DECLARE_PURCHASES_TO_TEAMMATES"
        
        "AbilityCooldown"       "30"
        "AbilityManaCost"       "0"
        
        "AbilitySpecial"
        {
            "01"
            {
                "var_type"      "FIELD_INTEGER"
                "bonus_damage"  "60"
            }
        }
    }
}
```

---

## 📁 units/ - 单位定义

所有非英雄单位的 KV 数据定义。

### 目录结构

| 目录 | 说明 |
|------|------|
| `boss/` | Boss 单位 |
| `buildings/` | 建筑物 |
| `minimap/` | 小地图标记 |
| `misc/` | 杂项单位 |
| `neutrals/` | 中立生物 |

### 单位文件示例

| 文件 | 说明 |
|------|------|
| `dota_fountain.txt` | 泉水 |
| `npc_dota_beastmaster_boar_*.txt` | 兽王野猪 (1-6级) |
| `npc_dota_brewmaster_earth_*.txt` | 酒仙土熊猫 |
| `npc_dota_broodmother_spiderling.txt` | 蜘蛛幼虫 |
| `npc_dota_enigma_eidolon_*.txt` | 谜团小鬼 |
| `npc_dota_furion_treant_*.txt` | 先知树人 |
| `npc_dota_lycan_wolf*.txt` | 狼人狼 |
| `npc_dota_lone_druid_bear1.txt` | 熊德熊 |
| `npc_dota_warlock_golem.txt` | 术士石像鬼 |

### 召唤物等级系统

许多召唤物有多个等级版本，对应技能等级：
- `npc_dota_enigma_eidolon_1.txt` - 1级小鬼
- `npc_dota_enigma_eidolon_6.txt` - 6级小鬼

### 单位 KV 格式示例

```
"DOTAUnits"
{
    "npc_dota_example_unit"
    {
        "BaseClass"             "npc_dota_creature"
        "Model"                 "models/example/example.vmdl"
        "ModelScale"            "1.0"
        "Level"                 "1"
        
        "StatusHealth"          "500"
        "StatusMana"            "200"
        "StatusHealthRegen"     "5"
        "StatusManaRegen"       "1"
        
        "MovementCapabilities"  "DOTA_UNIT_CAP_MOVE_GROUND"
        "MovementSpeed"         "325"
        
        "ArmorPhysical"         "2"
        "MagicalResistance"     "25"
        
        "AttackCapabilities"    "DOTA_UNIT_CAP_MELEE_ATTACK"
        "AttackDamageMin"       "30"
        "AttackDamageMax"       "35"
        "AttackRate"            "1.5"
        "AttackRange"           "128"
        
        "BountyGoldMin"         "20"
        "BountyGoldMax"         "25"
        "BountyXP"              "50"
        
        "Ability1"              "ability_name"
    }
}
```

---

## 📁 portraits/ - 头像配置

英雄选择界面头像显示配置。

---

## 🔧 开发指南

### 添加新技能

1. 在 `abilities/` 创建技能 KV 文件
2. 在 `npc_abilities_custom.txt` 添加 `#base` 引用
3. 在 `vscripts/abilities/` 创建对应 Lua 文件

### 添加新英雄

1. 在 `heroes/` 创建英雄 KV 文件
2. 在 `npc_heroes_custom.txt` 添加 `#base` 引用
3. 在 `herolist.txt` 添加英雄到白名单
4. 创建所有技能的 KV 和 Lua 文件

### 添加新物品

1. 在 `items/` 或子目录创建物品 KV 文件
2. 在 `npc_items_custom.txt` 添加 `#base` 引用
3. 在商店配置中添加物品
4. 如需主动效果，创建对应 Lua 文件

### 添加新单位

1. 在 `units/` 或子目录创建单位 KV 文件
2. 在 `npc_units_custom.txt` 添加 `#base` 引用
3. 如需 AI，在 `vscripts/units/` 创建 AI 脚本

---

## 📚 KV 文件格式说明

### 基本语法

```
"KeyName"
{
    "key1"    "value1"
    "key2"    "value2"
    
    "nested_key"
    {
        "inner_key"    "inner_value"
    }
}
```

### 引用其他文件

```
#base "path/to/other_file.txt"
```

### 继承和覆盖

```
"item_upgraded_version"
{
    "BaseClass"         "item_base_version"
    // 只需定义要覆盖的属性
    "ItemCost"          "6000"
}
```

---

## 📚 相关文档

- [VScripts 目录详解](../vscripts/DIRECTORY_GUIDE.md)
- [Game 目录详解](../../DIRECTORY_GUIDE.md)
- [项目主文档](../../../README_CN.md)
- [KV 格式文档](../../../docs/kv/)

---

*本文档用于说明 Open Angel Arena 的 npc 目录结构*
