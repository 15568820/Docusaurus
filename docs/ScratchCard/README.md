---
sidebar_position: 1
---

# 插件介绍

## 刮刮乐

### **适用版本**

> 1.8-1.20

### **依赖插件**

> - 必要: MythicMobs
> - 可选: PlayerPoints
> - 可选: Vault
> - 可选: NeigeItems
> - 可选: OriginAttribute
> - 可选: SX-Attribute

### **插件介绍**

> - 刮出的号码和中奖号码相同就获得对应奖励
> - 奖励支持MythicMobs,SX-Attribute,NeigeItems,OriginAttribute物品库
> - 奖励支持Vault,PlayerPoints货币

#### 插件指令

![](img/插件指令.png)

### **效果展示**

#### [【ScratchCard 使用视频】](https://www.bilibili.com/video/BV1XN411L7iQ/?share_source=copy_web&vd_source=92b2fd908671149c91aa9aa2d1163754)

![](img/效果展示1.png)

### **配置文件**

<details>
<summary>刮刮卡示例配置</summary>

  ```yaml
# GUI方案,对应路径 plugins/ScratchCard/gui/方案名.yml
gui: "test.yml"
# 中奖号码,0为随机,大于0为固定
win-number: 0
card:
  material: PAPER
  name: "§e§l花开富贵"
  lore:
    - "§d刮刮卡"
# 奖励列表
reward:
  # 可随意命名
  10000金币:
    # 显示的名字
    name: "§e10000金币"
    # 概率,1.0为100%
    probability: 0.5
    # 出现的权重
    weight: 100
    # 奖励列表
    # 参数 type(类型),
    # mm —— MythicMobs物品库
    # ni —— NeigeItems物品库
    # sx —— SX-Attribute物品库
    # money —— 金币
    # playerpoints —— PlayerPoints 点券
    # command —— 指令
    # message —— 消息提示
    #
    # 参数 id,物品库对应的物品id
    # 参数 amount,物品数量
    # 参数 command,类型 command 对应的指令参数
    # 参数 message,类型 message 对应的消息参数
    # 参数 server,类型 message 对应的参数,true为全服通知,false为仅该玩家通知
    list:
      - "type=money,amount=1000"
      - "type=message,message='§a恭喜玩家 §e%player_name% §a在花开富贵中开出了 §e10000金币'"
  500点券:
    # 显示的名字
    name: "§e500点券"
    # 概率,1.0为100%
    probability: 0.1
    # 出现的权重
    weight: 20
    # 奖励列表
    list:
      - "type=playerpoints,amount=500"
      - "type=message,message='§a恭喜玩家 §e%player_name% §a在花开富贵中开出了 §e500点券'"
  解锁材料:
    # 显示的名字
    name: "§e解锁材料"
    # 数量
    amount: 10
    # 概率,1.0为100%
    probability: 0.25
    # 出现的权重
    weight: 50
    # 奖励列表
    list:
      - "type=mm,id=解锁材料,amount=10"
      - "type=message,message='§a恭喜玩家 §e%player_name% §a在花开富贵中开出了 §e解锁材料'"
  ```

</details>


<details>
<summary>刮刮卡GUI示例配置</summary>

  ```yaml
# GUI标题
title: "§e§l花         开         富         贵"
# 中奖号码刮开前
win-scratch-after: W
# 中奖号码
win-number: w
# 我的号码刮开前模板
my-scratch-after: M
# 我的号码
my-number: m
status:
  win: "§c已中奖"
  fail: "§f无中奖"
# 页面布局
layout:
  - "####W####"
  - "#########"
  - "#MMMMMMM#"
  - "#MMMMMMM#"
  - "#MMMMMMM#"
  - "#########"
#布局材料及槽位
materials:
  "#":
    material: GRAY_STAINED_GLASS_PANE
    name: " "
    lore:
      - "§f "
  "W":
    material: MUSHROOM_STEW
    name: "§f点击刮开中奖号码"
    lore:
      - "§f"
  "w":
    material: SUNFLOWER
    name: "§f中奖号码: §f§l%number%"
    lore:
      - "§f "
  "M":
    material: MUSHROOM_STEW
    name: "§f点击刮开"
    lore:
      - " "
  "m":
    material: BOWL
    name: "§f号码: §6§l%number%"
    lore:
      - "§f奖励: %reward%"
      - ""
      - "%status%"
  ```

</details>

