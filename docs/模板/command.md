## 权限

##### 本插件默认无需配置任何权限,服主开箱即用

##### 很多下面涉及都类型不知道的 低版本请使用tab自动补全,1.12以上会自动提醒

| 权限                        | 用途                       | 默认拥有者 |
|---------------------------|--------------------------|-------|
| playerTask.addList        | 新增任务                     | op    |
| playerTask.addDemand      | 新增任务目标                   | op    |
| playerTask.addReward      | 新增任务奖励                   | op    |
| playerTask.addShop        | 新增任务币商城物品                | op    |
| playerTask.open           | 每日任务gui                  | op    |
| playerTask.shop           | 任务币商城gui                 | op    |
| playerTask.create         | 创建任务                     | op    |
| playerTask.delete         | 删除任务                     | op    |
| playerTask.view           | 管理任务                     | op    |
| playerTask.vip            | vio权限                    | op    |
| playerTask.getToday       | 立即获取今日任务                 | op    |
| playerTask.delToday       | 清空今日任务列表和全部玩家的任务(1.4.1+) | op    |
| playerTask.delShop        | 删除对应id的任务币商城物品           | op    |
| playerTask.reload         | 重载配置                     | op    |
| playerTask.edit           | 编辑任务(1.7.1+)             | op    |
| playerTask addNpcTask     | 添加npc任务(1.6.0+)          | op    |
| playerTask delNpcTask     | 删除npc任务(1.6.0+)          | op    |
| playerTask.setRarity      | 编辑任务稀有度(1.8.7+）          | op    |
| playerTask.changeItem     | 生成任务卷轴 (1.9.0+)          | op    |
| playerTask.setDescription | 添加任务描述(1.9.7+)           | op    |
| playerTask.coin           | 操作玩家任务币(1.13.2+)         | op    |

## 指令(管理员):

| 指令                                                              | 用途                                                                 |
|-----------------------------------------------------------------|--------------------------------------------------------------------|
| /plk addDemand [目标类型] [数量]                                      | 添加任务目标(需要主手持有对应物品)                                                 |
| /plk addReward [奖励类型] [数量]                                      | 添加任务奖励(如果奖励类型是物品需要主手持有对应物品)                                        |
| /plk addShop [类型] [价格]                                          | 添加任务币商城物品奖励(类型:限购一次:once;无限购买:infinite)                            |
| /plk create [任务名称] (任务类型) (任务稀有度)                               | 使用gui来创建任务(推荐)                                                     |
| /plk addList [任务名称] [称号目标id] [任务奖励id]                           | 使用指令方式添加一个任务                                                       |
| /plk delete [类型] [对应id]                                         | 使用指令方式删除任务,任务目标,任务奖励                                               |
| /plk view [类型]                                                  | 使用gui里查看和管理 类型,[list:任务,demand:任务目标,reward:任务奖励,例如: /plk view list |
| /plk getToday                                                   | 立即执行一次获取今日任务程序                                                     |
| /plk delToday                                                   | 清空今日任务列表和全部玩家的任务(1.4.1+)                                           |
| /plk delShop [对应ID]                                             | 删除对应id的任务币商城物品                                                     |
| /plk getIp                                                      | 获取ip                                                               |
| /plk reload                                                     | 重载配置                                                               |
| /plk edit [任务id]                                                | 使用gui编辑任务(1.7.1+)                                                  |
| /plk addNpcTask [任务id] [npcId] [是否永久任务] [可完成次数] [冷却时间] (前置任务id) | 添加npc任务(1.6.0+)                                                    |
| /plk delNpcTask [npcId]                                         | 删除npc任务(1.6.0+)                                                    |
| /plk setRarity [任务id] [稀有度]                                     | 编辑任务稀有度（1.8.7+）                                                    |
| /plk changeItem [任务id] (玩家名称)                                   | 生成任务卷轴(1.9.0+)                                                     |
| /plk setDescription [任务id] [任务描述]                               | 添加任务描述(1.9.7+)                                                     |
| /plk coin [类型] [玩家名] [数量]                                       | 操作玩家任务币数量(1.13.2)                                                  |

## 指令(玩家):

| 指令        | 用途         |
|-----------|------------|
| /plk open | 打开每日任务gui  |
| /plk shop | 打开任务币商城gui |

### 目前支持的任务目标类型如下

```
craftItem 合成
blockBreak 挖掘
Fish 垂钓
Interact 放置
kill 击杀MM怪物
consume 消耗物品
killNormal 击杀普通怪物
submit 提交物品
killPlayer 击杀玩家(1.13.3+)
enchantment 附魔(1.13.3+)
```

[附魔类型WIKI](https://bukkit.windit.net/javadoc/org/bukkit/enchantments/Enchantment.html)

### 目前支持的任务奖励类型如下

```
vault 金币
playerPoints 点券
coin 任务币
itemStack 物品
command 命令
```

### 命令类型说明

```
# 玩家执行指令,中间的0代表按照玩家身份执行,如果玩家没权限会执行失败
/plk addReward command 0 eco#give#${player}#666
# 玩家执行指令,中间的1代表按照op身份执行
/plk addReward command 1 eco#give#${player}#666
```

### 任务类型说明

> 任务类型分为 everyday(每日任务)  npc(NPC任务) 不互通
