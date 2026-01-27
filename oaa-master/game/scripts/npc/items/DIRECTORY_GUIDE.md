# Items 目录结构说明

本目录包含 Open Angel Arena 所有物品的 KV 数据定义文件。

---

## 📁 目录结构概览

```
items/
├── basic/                  # 基础组件物品
├── blinks/                 # 闪烁类物品
├── boss/                   # Boss 掉落物品
├── custom/                 # OAA 自定义物品
├── dev/                    # 开发测试物品
├── neutral/                # 中立物品
└── item_*.txt              # 标准物品定义文件
```

---

## 📁 子目录说明

### basic/ - 基础物品

游戏中的基础组件物品，用于合成高级装备：

- 基础属性物品
- 小件装备
- 消耗品

### blinks/ - 闪烁类物品

所有具有位移效果的物品：

- 闪烁匕首及其升级版本
- 其他位移类物品

### boss/ - Boss 掉落物品

击杀 Boss 后获得的特殊物品：

- Boss 专属掉落
- 稀有奖励物品

### custom/ - 自定义物品

OAA 独创的自定义物品：

- 天使光环 (Angels Halo)
- 泡泡法球 (Bubble Orb)
- 毁灭者 (Devastator)
- 幽灵黑皇杖 (Ghost King Bar)
- 魔法神灯 (Magic Lamp)
- 更多独特物品...

### dev/ - 开发测试物品

供开发和测试使用的物品：

- 调试用物品
- 测试属性物品

> ⚠️ 仅用于开发环境

### neutral/ - 中立物品

通过野怪掉落获得的中立物品。

---

## 📄 物品升级系统

OAA 的核心特色之一是物品升级系统。大部分物品可以升级到 5 级。

### 命名规则

| 等级 | 命名格式 | 示例 |
|------|---------|------|
| 1级 | `item_xxx.txt` | `item_abyssal_blade.txt` |
| 2级 | `item_xxx_2.txt` | `item_abyssal_blade_2.txt` |
| 3级 | `item_xxx_3.txt` | `item_abyssal_blade_3.txt` |
| 4级 | `item_xxx_4.txt` | `item_abyssal_blade_4.txt` |
| 5级 | `item_xxx_5.txt` | `item_abyssal_blade_5.txt` |

### 升级物品列表

以下物品支持多级升级：

| 物品 | 最高等级 | 说明 |
|------|---------|------|
| Abyssal Blade | 5 | 深渊之刃 |
| Aeon Disk | 5 | 永恒之盘 |
| Armlet | 5 | 臂章 |
| Assault Cuirass | 5 | 强袭胸甲 |
| Battle Fury | 5 | 狂战斧 |
| Black King Bar | 5 | 黑皇杖 |
| Bloodstone | 5 | 血精石 |
| Bloodthorn | 5 | 血棘 |
| Butterfly | 5 | 蝴蝶 |
| Crimson Guard | 5 | 赤红甲 |
| Daedalus | 5 | 代达罗斯之殇 |
| Disperser | 5 | 散华 |
| Eternal Shroud | 5 | 永恒之罩 |
| Ethereal Blade | 5 | 虚灵之刃 |
| Glimmer Cape | 5 | 微光披风 |
| Gleipnir | 5 | 格莱普尼尔 |
| Harpoon | 5 | 鱼叉 |
| Heart of Tarrasque | 5 | 恐鳌之心 |
| Heaven's Halberd | 5 | 天堂之戟 |
| Helm of the Overlord | 5 | 支配头盔 |
| Hurricane Pike | 5 | 飓风长戟 |
| Kaya and Sange | 5 | 散慧对剑 |
| Khanda | 5 | 匕达 |
| Lotus Orb | 5 | 清莲宝珠 |
| Manta Style | 5 | 幻影斧 |
| Meteor Hammer | 5 | 陨星锤 |
| Mjollnir | 5 | 雷神之锤 |
| Monkey King Bar | 5 | 金箍棒 |
| Nullifier | 5 | 否决坠饰 |
| Octarine Core | 5 | 玲珑心 |
| Parasma | 5 | 帕拉斯玛 |
| Pipe of Insight | 5 | 洞察烟斗 |
| Radiance | 5 | 辉耀 |
| Refresher Orb | 5 | 刷新球 |
| Revenant's Brooch | 5 | 亡魂胸针 |
| Sange and Yasha | 5 | 散夜对剑 |
| Satanic | 5 | 撒旦之邪力 |
| Scythe of Vyse | 5 | 邪恶镰刀 |
| Shiva's Guard | 5 | 希瓦的守护 |
| Silver Edge | 5 | 白银之锋 |
| Eye of Skadi | 5 | 斯嘉蒂之眼 |
| Solar Crest | 5 | 炎阳纹章 |
| Linken's Sphere | 5 | 林肯法球 |
| Spirit Vessel | 5 | 魂之灵瓮 |
| Wind Waker | 5 | 风之杖 |
| Yasha and Kaya | 5 | 夜散对剑 |

### 特殊升级物品

| 物品 | 最高等级 | 说明 |
|------|---------|------|
| Dagon | 9 | 达贡之神力（1-9级） |
| Aghanim's Scepter | 5 | 阿哈利姆神杖 |

---

## 📄 物品文件格式

### 基本结构

```
"DOTAAbilities"
{
    "item_example"
    {
        // 基础信息
        "BaseClass"             "item_lua"
        "ScriptFile"            "items/example.lua"
        "AbilityTextureName"    "item_example"
        
        // 物品行为
        "AbilityBehavior"       "DOTA_ABILITY_BEHAVIOR_IMMEDIATE | DOTA_ABILITY_BEHAVIOR_NO_TARGET"
        
        // 商店信息
        "ItemCost"              "5000"
        "ItemShopTags"          "damage;hard_to_tag"
        "ItemQuality"           "epic"
        "ItemAliases"           "example"
        "ItemDeclarations"      "DECLARE_PURCHASES_TO_TEAMMATES"
        
        // 主动技能属性
        "AbilityCooldown"       "30"
        "AbilityManaCost"       "0"
        
        // 物品属性
        "AbilitySpecial"
        {
            "01"
            {
                "var_type"      "FIELD_INTEGER"
                "bonus_damage"  "60"
            }
            "02"
            {
                "var_type"      "FIELD_FLOAT"
                "bonus_attack_speed"  "25"
            }
        }
    }
}
```

### 升级物品结构

升级物品通常使用 `ItemRequirements` 定义合成配方：

```
"item_example_2"
{
    "BaseClass"             "item_lua"
    "ScriptFile"            "items/example.lua"
    
    "ItemCost"              "0"
    "ItemRecipe"            "0"
    
    "ItemRequirements"
    {
        "01"    "item_example;item_upgrade_core"
    }
    
    "AbilitySpecial"
    {
        "01"
        {
            "var_type"      "FIELD_INTEGER"
            "bonus_damage"  "90"    // 比1级更高
        }
    }
}
```

---

## 📋 物品分类

### 按稀有度

| 稀有度 | ItemQuality 值 | 说明 |
|--------|---------------|------|
| 普通 | `component` | 基础组件 |
| 稀有 | `rare` | 稀有物品 |
| 史诗 | `epic` | 史诗物品 |
| 传说 | `legendary` | 传说物品 |

### 按类型标签 (ItemShopTags)

| 标签 | 说明 |
|------|------|
| `damage` | 伤害类 |
| `attack_speed` | 攻速类 |
| `armor` | 护甲类 |
| `health` | 生命类 |
| `mana` | 魔法类 |
| `regen` | 恢复类 |
| `str` | 力量类 |
| `agi` | 敏捷类 |
| `int` | 智力类 |
| `hard_to_tag` | 难以分类 |

---

## 🔧 开发指南

### 添加新物品

1. 在适当的子目录或根目录创建物品 KV 文件
2. 在 `npc_items_custom.txt` 添加 `#base` 引用
3. 如需主动效果，在 `vscripts/items/` 创建 Lua 脚本
4. 在商店配置中添加物品
5. 添加本地化字符串

### 添加物品升级

1. 创建对应等级的 KV 文件 (item_xxx_2.txt 等)
2. 设置 `ItemRequirements` 定义升级配方
3. 增加属性数值
4. 更新商店配置

### 物品图标

物品图标文件应放置在：
- `content/panorama/images/items/`

命名格式：`item_xxx.png`

---

## 📚 相关文档

- [NPC 目录详解](../DIRECTORY_GUIDE.md)
- [VScripts Items 目录](../../vscripts/items/)
- [商店配置](../../shops/)
- [项目主文档](../../../../README_CN.md)

---

*本文档用于说明 Open Angel Arena 的 items 目录结构*
