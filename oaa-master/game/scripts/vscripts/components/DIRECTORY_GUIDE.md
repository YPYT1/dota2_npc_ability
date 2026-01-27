# Components 目录结构说明

本目录包含 Open Angel Arena 的所有游戏系统组件，采用模块化设计，每个组件负责一个独立的游戏功能系统。

---

## 📁 目录结构概览

```
components/
├── index.lua               # 组件索引和加载器
├── abilities/             # 技能系统组件
├── boss/                  # Boss 战斗系统
├── bottlepass/            # 瓶子通行证系统
├── capturepoints/         # 占领点系统
├── cave/                  # 洞穴探索系统
├── corepoints/            # 核心积分系统
├── courier/               # 信使系统
├── creeps/                # 小兵系统
├── devcheats/             # 开发者作弊命令
├── doors/                 # 门控制系统
├── duels/                 # 决斗系统
├── experience/            # 经验系统
├── filters/               # 过滤器系统
├── glyph/                 # 防御符文系统
├── gold/                  # 金币系统
├── heroselection/         # 英雄选择系统
├── items/                 # 物品系统
├── minimap/               # 小地图系统
├── music/                 # 音乐系统
├── player/                # 玩家系统
├── points/                # 积分系统
├── progression/           # 进度系统
├── reflexfilters/         # 反射过滤器
├── runes/                 # 符文系统
├── saveload/              # 存档/加载系统
├── sparks/                # 火花效果系统
├── startingitems/         # 初始物品系统
├── statprovider/          # 属性提供者
├── surrender/             # 投降系统
├── team_select/           # 队伍选择系统
└── zonecontrol/           # 区域控制系统
```

---

## 📄 入口文件

### `index.lua`

**组件索引和加载器**

负责加载和初始化所有游戏组件。在游戏启动时按顺序加载各个系统。

```lua
-- 示例：组件加载
require("components/gold")
require("components/experience")
require("components/duels")
-- ...
```

---

## 📁 组件详解

### abilities/ - 技能系统组件

管理游戏中技能相关的全局逻辑：

- 技能冷却管理
- 技能学习规则
- 技能等级上限控制
- 阿哈利姆神杖效果处理

---

### boss/ - Boss 战斗系统

管理游戏中所有 Boss 战斗：

| 功能 | 说明 |
|------|------|
| Boss 生成 | 定时在指定位置生成 Boss |
| Boss AI | Boss 战斗行为控制 |
| Boss 掉落 | 击杀 Boss 后的奖励分配 |
| Boss 阶段 | 多阶段 Boss 战斗管理 |
| Boss 血条 | 自定义 Boss 血条 UI |

**支持的 Boss 类型**：
- 熊王 Boss
- 狼人 Boss
- 岩浆 Boss
- 蜘蛛 Boss
- 食人魔坦克 Boss
- 折磨者 Boss
- 肉山

---

### bottlepass/ - 瓶子通行证系统

类似战斗通行证的进度系统：

- 任务追踪
- 奖励解锁
- 进度存储

---

### capturepoints/ - 占领点系统

控制地图上的战略占领点：

| 功能 | 说明 |
|------|------|
| 占领逻辑 | 玩家站在点上逐渐占领 |
| 占领进度 | 占领百分比计算 |
| 占领奖励 | 成功占领后的团队奖励 |
| 争夺机制 | 多队同时争夺时的处理 |
| 视觉反馈 | 占领进度圆环特效 |

---

### cave/ - 洞穴探索系统

PvE 洞穴冒险系统：

- 洞穴区域生成
- 怪物刷新
- 宝藏和奖励
- 难度递增

---

### corepoints/ - 核心积分系统

游戏核心积分计算：

- 击杀积分
- 助攻积分
- 目标积分
- 胜利条件判定

---

### courier/ - 信使系统

自定义信使行为：

- 信使生成
- 信使升级
- 信使保护
- 团队共享

---

### creeps/ - 小兵系统

小兵和野怪管理：

| 功能 | 说明 |
|------|------|
| 小兵生成 | 定时生成线上小兵 |
| 小兵强化 | 随时间增强小兵属性 |
| 超级兵 | 破塔后的超级兵生成 |
| 野怪刷新 | 野区中立生物刷新 |
| 掉落系统 | 小兵和野怪的金币/物品掉落 |

---

### devcheats/ - 开发者作弊命令

调试和测试用的作弊命令：

```
-gold 10000       # 给予金币
-xp 10000         # 给予经验
-lvl 25           # 设置等级
-refresh          # 刷新技能冷却
-kill             # 击杀目标
-spawn boss_name  # 生成单位
```

> ⚠️ 仅在开发模式下可用

---

### doors/ - 门控制系统

地图上门的开关控制：

- 定时开关
- 条件触发开关
- 团队专属门
- 动画和音效

---

### duels/ - 决斗系统

OAA 核心机制 - 强制 PvP 决斗：

| 功能 | 说明 |
|------|------|
| 决斗触发 | 定时强制所有玩家决斗 |
| 决斗区域 | 传送到专用决斗区域 |
| 决斗规则 | 死亡惩罚、退出惩罚 |
| 决斗奖励 | 胜利方获得金币和积分 |
| 决斗保护 | 决斗期间的特殊状态 |
| 越位系统 | 未参与决斗的处罚 |

**决斗流程**：
1. 预警阶段（倒计时）
2. 传送阶段（强制传送到决斗场）
3. 战斗阶段（玩家对战）
4. 结算阶段（计算胜负和奖励）
5. 恢复阶段（回到原位置）

---

### experience/ - 经验系统

自定义经验获取和分配：

- 击杀经验
- 助攻经验
- 被动经验获取
- 经验分享规则
- 等级上限控制

---

### filters/ - 过滤器系统

游戏事件过滤器：

- 伤害过滤
- 治疗过滤
- 金币过滤
- 经验过滤
- 击杀过滤

用于全局修改游戏机制。

---

### glyph/ - 防御符文系统

团队防御符文机制：

- 符文冷却
- 建筑免疫
- 使用通知

---

### gold/ - 金币系统

自定义金币获取和消费：

| 功能 | 说明 |
|------|------|
| 击杀金币 | 击杀英雄获得金币 |
| 助攻金币 | 助攻分成 |
| 被动金币 | 定时获得金币 |
| 建筑金币 | 摧毁建筑奖励 |
| 死亡损失 | 死亡时损失金币 |

---

### heroselection/ - 英雄选择系统

自定义英雄选择流程：

- 选择界面
- 随机英雄
- 重新选择
- 禁用英雄
- 队伍平衡

---

### items/ - 物品系统

物品相关全局逻辑：

- 物品合成
- 物品升级（OAA 特色）
- 物品冷却共享
- 物品限购
- 掉落物品

---

### minimap/ - 小地图系统

小地图自定义显示：

- 自定义图标
- Boss 位置标记
- 占领点状态
- 队友位置

---

### music/ - 音乐系统

背景音乐管理：

- 阶段音乐切换
- 战斗音乐
- 胜利/失败音乐
- 音量控制

---

### player/ - 玩家系统

玩家相关逻辑：

- 玩家连接/断开
- 玩家数据存储
- 玩家设置
- 掉线重连

---

### points/ - 积分系统

游戏积分管理：

- 团队积分
- 个人积分
- 积分排行
- 胜利条件

---

### progression/ - 进度系统

游戏进度管理：

- 游戏阶段
- 时间进度
- 难度递增
- 事件触发

---

### reflexfilters/ - 反射过滤器

技能反射相关过滤：

- 反弹伤害计算
- 反射条件判定
- 无限反射防护

---

### runes/ - 符文系统

自定义符文机制：

| 符文类型 | 效果 |
|---------|------|
| 双倍伤害 | 增强版双倍伤害 |
| 加速 | 增强版加速 |
| 隐身 | 增强版隐身 |
| 恢复 | 增强版恢复 |
| 赏金 | 增强版赏金 |
| 幻象 | 增强版幻象 |
| 自定义符文 | OAA 特有符文 |

---

### saveload/ - 存档/加载系统

游戏状态持久化：

- 玩家数据保存
- 断线重连恢复
- 跨局数据

---

### sparks/ - 火花效果系统

特殊视觉效果：

- 技能触发火花
- 暴击火花
- 伤害数字

---

### startingitems/ - 初始物品系统

游戏开始时的物品分配：

- 初始金币
- 免费物品
- 推荐出门装

---

### statprovider/ - 属性提供者

全局属性修改器：

- 属性加成
- 属性缩放
- 属性上限

---

### surrender/ - 投降系统

团队投降机制：

| 功能 | 说明 |
|------|------|
| 发起投降 | 玩家发起投降投票 |
| 投票机制 | 需要多数同意 |
| 冷却时间 | 投降失败后的冷却 |
| 最早时间 | 游戏开始后最早可投降时间 |

---

### team_select/ - 队伍选择系统

自定义队伍选择：

- 队伍分配
- 队伍平衡
- 队伍切换

---

### zonecontrol/ - 区域控制系统

地图区域控制：

- 禁区定义
- 区域效果
- 区域触发器
- 安全区域

---

## 🔧 开发指南

### 创建新组件

1. **创建组件目录**
   ```
   components/my_component/
   ```

2. **创建入口文件**
   ```lua
   -- components/my_component/init.lua
   
   if MyComponent == nil then
       MyComponent = class({})
   end
   
   function MyComponent:Init()
       -- 初始化逻辑
   end
   
   -- 注册事件监听
   ListenToGameEvent("game_rules_state_change", Dynamic_Wrap(MyComponent, 'OnGameStateChange'), MyComponent)
   ```

3. **在 index.lua 中注册**
   ```lua
   require("components/my_component/init")
   ```

### 组件通信

组件之间通过事件系统通信：

```lua
-- 发送自定义事件
CustomGameEventManager:Send_ServerToAllClients("my_event", {data = value})

-- 监听自定义事件
CustomGameEventManager:RegisterListener("my_event", function(_, data)
    -- 处理事件
end)
```

### 组件依赖

如果组件依赖其他组件，在初始化时检查：

```lua
function MyComponent:Init()
    if not Gold then
        print("Warning: MyComponent requires Gold component")
        return
    end
    -- 继续初始化
end
```

---

## 📚 相关文档

- [VScripts 目录详解](../DIRECTORY_GUIDE.md)
- [NPC 目录详解](../../npc/DIRECTORY_GUIDE.md)
- [Game 目录详解](../../../DIRECTORY_GUIDE.md)
- [项目主文档](../../../../README_CN.md)

---

*本文档用于说明 Open Angel Arena 的 components 目录结构*
