---
sidebar_position: 1
---

# 奖励配置

### **参数说明**

#### **奖励参数**

| 参数      | 说明                                      |
|---------|-----------------------------------------|
| name    | 奖励显示的名字                                 |
| id      | 物品库对应的物品id                              |
| amount  | 奖励为物品则物品数量,奖励为货币则货币数量                   |
| command | 类型 command 对应的指令参数                      |
| message | 类型 message 对应的消息参数                      |
| server  | 类型 message 对应的参数,true为全服通知,false为仅该玩家通知 |

| ==================== | ==================================== |

#### **type(奖励类型)**

| 值                    | 说明                                     |
|----------------------|----------------------------------------|
| mm                   | MythicMobs物品库                          |
| ni                   | NeigeItems物品库                          |
| sx                   | SX-Attribute物品库                        |
| playerpoints         | PlayerPoints 点券                        |
| money                | 金币                                     |
| command              | 指令                                     |
| message              | 消息提示                                   |
| ==================== | ====================================== |

#### **示例**

<details>
<summary>奖励消息提示</summary>

  ```yaml
# 玩家提醒
- "type=message,message='§a恭喜玩家 §e%player_name% §a在花开富贵中开出了 §e10000金币'"
# 全服提醒提醒
- "type=message,message='§a恭喜玩家 §e%player_name% §a在花开富贵中开出了 §e10000金币',server=true"
  ```

</details>

<details>
<summary>奖励1000金币</summary>

  ```yaml
- "type=money,amount=1000"
  ```

</details>

<details>
<summary>奖励500点券</summary>

  ```yaml
- "type=playerpoints,amount=500"
  ```

</details>


<details>
<summary>奖励MythicMobs物品</summary>

  ```yaml
- "type=mm,id=物品库中的ID,amount=1"
  ```

</details>

<details>
<summary>奖励SX-Attribute物品</summary>

  ```yaml
- "type=sx,id=物品库中的ID,amount=1"
  ```

</details>

<details>
<summary>奖励NeigeItems物品</summary>

  ```yaml
- "type=ni,id=物品库中的ID,amount=1"
  ```

</details>

<details>
<summary>奖励OriginAttribute物品</summary>

  ```yaml
- "type=oa,id=物品库中的ID,amount=1"
  ```

</details>
