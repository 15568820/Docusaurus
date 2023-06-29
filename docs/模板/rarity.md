### 任务稀有度介绍

> 在1.8.7+版本新增任务稀有度概念

config.yml中新增

```
# 任务稀有度刷新概率(Mission Rarity Refresh Probability)
# 颜色是推荐设置的任务名称颜色，方便玩家识别任务(The colour is the recommended setting of the mission name colour to make it easier for players to identify the mission)
rarity:
# 普通任务（白色） normal task (white) &f
normal: 0.8
# 高级任务（蓝色）advanced task (blue) &1
advanced: 0.5
# 稀有任务（紫色） rare task (purple) &5
rare: 0.3
# 罕见任务（粉色）rarer task (pink) &d
rarer: 0.2
# 史诗任务（橙色）epic task (orange) &e
epic: 0.1
# 神话任务 (渐变色) mythical task (gradient) &e&l
mythical: 0.01
不做任何限制,并享受售后,一对一服务,定制需求优先采纳等尊贵特权
```

### 稀有度如上,默认有这些稀有度

1. 每日随机生成的任务会根据上面配置按照概率生成,数量不足填充普通任务(历史任务全部为普通)
2. 主要目的: 玩家想要高稀有度的任务就必须一直刷新每日任务,提高收益
3. 新增任务指令变更为/plk create [任务名称] (任务类型) (任务稀有度)
4. 或者使用/plk setRarity [任务id] [稀有度] 来进行设置任务的稀有度