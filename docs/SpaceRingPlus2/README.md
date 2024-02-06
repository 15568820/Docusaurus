---
sidebar_position: 1
---

# 插件介绍

## 更好的灵魂空间

### **适用版本**

> 1.9-1.20

### **依赖插件**

> - 必要: MythicMobs
> - 可选: PlayerPoints
> - 可选: Vault
> - 可选: NeigeItems
> - 可选: OriginAttribute
> - 可选: SX-Attribute
> - 可选: PlaceholderAPI
> - 可选: SimpleLib

### **插件介绍**

> - 支持JSON,SQLite,MySQL三种存储方式
> - 支持槽位解锁数量,所需金币,所需点券要求,每页最多可放入45格物品
> - 支持MythicMobs,SX-Attribute,NeigeItems,OriginAttribute物品给予玩家仓库
> - 支持数据备份和数据导入
> - 支持完整导入KLRing玩家数据
> - 自动拾取MythicMobs怪物Drops
> - 自动拾取地上掉落物
> - 自定义设置每页解锁方案
> - 自定义设置不同权限玩家页数上限
> - 仓库快捷垃圾桶
> - 仓库快捷分解

#### 插件指令

![](img/插件指令.png)

### **效果展示**

![](img/效果展示1.png)
![](img/效果展示2.png)
![](img/效果展示3.png))

### **快捷分解**

![](img/快捷分解.png))
![](img/分解详情.png)

### **仓库剩余空间**

![](img/仓库充足.png)
![](img/仓库过半.png))
![](img/仓库已满.png)

### **配置文件**

<details>
<summary>config.yml</summary>

  ```yaml
# 您的授权码
code: "IKUN-JNTM-SZ666-SUSHAN"
database:
  # 存储方式 JSON,SQLITE,MYSQL
  type: JSON
  # 数据文件存储路径(不需要勿使用该参数)
  # path: "plugins/SpaceRingPlus2/data"

  # 数据库
  mysql:
    host: localhost
    port: 3306
    user: root
    password: root
    database: minecraft
# 该配置只生效于srg give,不生效srp give
give:
  # 给予默认倍率
  default: 1
  # 给予倍率配置，格式: 权限节点:倍率
  # 同时拥有多个权限将不叠加,优先生效第一个
  permission:
    "vip.vip1": 2
# 备份
backup:
  # 备份间隔,支持单位: d,h,m,s
  # 例如: 1h30m
  period: 8h
  # 保留备份文件数量
  reserve: 100
spacePage:
  # 不同点击方式放入和取出的数量
  # 填9999这样的大值可以实现全部存入或者是全部取出
  # 鼠标左键
  left_click: 1
  # 鼠标右键
  right_click: 64
  # Shift + 鼠标左键键
  shift_left_click: 9999
  # Shift + 鼠标右键
  shift_right_click: 9999
# 空间戒指
ring:
  material: SLIME_BALL
  name: "§e空间戒指"
  lore:
    - "§c§m                       "
    - "§7点 击 打开空间默认页"
    - "§7Shift + 右键打开首页"
    - "§7Shift + 左键切换模式"
    - "§c§m                       "
    - "%state%自动拾取"
  enable: "§a已开启"
  disable: "§c已关闭"
  # 是否允许丢弃
  drop: false
  ```

</details>


<details>
<summary>gui.yml</summary>

  ```yaml
  HomePage:
  Title: "§c§l灵魂空间"
  enough:
    Name: "§a仓库 %pageNum% (%use%/%volume%)"
    Id: 160
    Data: 5
    Lore:
      - "§f当前空位充足"
  some:
    Name: "§e仓库 %pageNum% (%use%/%volume%)"
    Id: 160
    Data: 1
    Lore:
      - "§f当前仓库还有一些空位"
  full:
    Name: "§c仓库 %pageNum% (%use%/%volume%)"
    Id: 160
    Data: 14
    Lore:
      - "§f当前仓库已没有空位！"
  SpacePage:
    Title: "§c§l仓库 §a第§e%pageNum%§a页"
    # 自定义按钮,支持以下变量+PAPI变量
    # 本页已用空间 %use%
    # 本页剩余空间 %volume%
    # 解锁所需材料 %material%
    # 解锁材料数量 %amount%
    # 解锁所需金币 %money%
    # 解锁所需点券 %point%
    # 每次解锁格数 %unlock%
    # 本页堆叠上限 %stack%
    Custom:
      # 可以按照该模板自行添加修改
      intro:
        Id: 54
        Data: 0
        Name: "§e当前容量: §f%use%/%volume%"
        Lore:
          - "§a解锁材料: §e%material%§fX%amount%"
          - "§a解锁金币: §f%money%"
          - "§a解锁点券: §f%point%"
          - "§a解锁格数: §f%unlock%"
          - "§a堆叠上限: §f%stack%"
          - "§f"
          - "§a单击左键 §f存入/取出 §a1个"
          - "§a单击右键 §f存入/取出 §a64个"
          - "§a单击+SHIFT §f存入/取出 §a全部"
        # 按钮位置不要填灵魂空间存储区域，否则会出问题
        Index: 49
          # 后台执行指令
        # Commands:
        # 默认后台执行
        # - "msg %player_name% 点击1成功"
        # 玩家执行
        # - "player:msg %player_name% 点击1成功"
        # OP执行
        # - "op:msg %player_name% 点击1功"
    # 魂珠增加的lore
    Item:
      Lore:
        - " "
        - "§a数量: §e%amount%"
    Trash:
      Id: 327
      Data: 0
      Name: "§2§l灵魂空间 - §c§l垃圾桶"
      Lore:
        - "§c点击切换至垃圾桶页面"
      Index: 50
      Title: "§c§l垃圾桶"
    # 未解锁
    Lock:
      Name: "§c未解锁"
      Id: 160
      Data: 15
      Lore:
        - "§f点击解锁"
      Index: 8
    # 上一页
    PageUp:
      Name: "§f上一页"
      Id: 262
      Data: 0
      Lore:
        - "§a点击打开上一页"
    # 下一页
    PageDown:
      Name: "§f下一页"
      Id: 262
      Data: 0
      Lore:
        - "§a点击打开下一页"

  ```

</details>

<details>
<summary>unlock.yml</summary>

  ```yaml
homePage:
# 使用该功能后玩家默认仓库为9页
# 格式仓库页数大小: 权限
# 仓库大小应为9的倍数,最大54
# 需要开启该功能把以下注释删掉即可
# 18: "srp.page.18"
# 27: "srp.page.27"
# 36: "srp.page.36"
# 45: "srp.page.45"
# 54: "srp.page.54"

# 解锁方案
unlockSlot:
  # 默认所有页面的解锁配置
  default:
    # 默认容量
    size: 0
    # 每次解锁的格子数
    unlock: 9
    # 物品堆叠上限, 0为不限制
    stack: 0
    # 解锁材料,填写mm物品名
    # 所需前置 MythicMobs
    # 留空则不需要解锁材料, 正确："" 错误: " "
    material: "解锁材料"
    # 所需解锁材料的数量
    amount: 1
    # 解锁所需点券,填0则不需要
    # 所需前置 PlayerPoints
    point: 100
    # 解锁所需金币,填0则不需要
    # 所需前置 Vault
    money: 100
  # 第一页解锁配置,配置第二页第三页同理
  1:
    size: 9
    unlock: 9
    stack: 0
    material: "解锁材料"
    amount: 1
    point: 100
    money: 100
  ```

</details>



<details>
<summary>message.yml</summary>

  ```yaml
prefix: "§8[§c系统§8] "
reload: "§a配置文件重载成功"
permission_false: "§a您的权限不够"
param_false: "§a参数不完整"
online_false: "§a玩家 §e{0} §a不在线"
player_null: "§a请输入玩家名."
exists_false: "§a文件 §e{0} §a不存在"
look_warn: "§a如果玩家在其它子服在线,本次操作若修改玩家数据将无效"
next_page_false: "§a这已经是最后一页了"
unlock_true: "§a解锁成功."
add_full: "§a空间已满,请解锁更多的槽位"
add_page: "§a请到第 §e{0} §a页存储该物品"
item_false: "§a该物品不能放入空间内"
item_stack_limit: "§a该物品的存储数量已上限"
ring_give_true: "§a空间戒指已给予玩家 §e{0}"
ring_enable_true: "§a空间戒指拾取模式: §e已开启"
ring_enable_false: "§a空间戒指拾取模式: §c已关闭"
ring_drop_false: "§a空间戒指拾禁止丢弃"
ring_inv_false: "§a空间戒指拾禁止放入"
unlock_material_null: "§a解锁材料 §e{0} §a设置不正确,请联系服务器管理员解决"
unlock_material_false: "§a您没有足够的解锁材料 {0}"
unlock_money_false: "§a解锁该槽位需要 §e{0} §a金币"
unlock_point_false: "§a解锁该槽位需要 §e{0} §a点券"
space_add_true: "§a物品 §e{0}§fX{1} §a已进入灵魂空间第§e {2} §a页"
space_add_false: "§a灵魂空间已满,物品 §e{0}§fX{1} §a已进入背包"
inventory_add_true: "§a物品 §e{0}§fX{1} §a已进入背包"
backup_ing: "§a数据正在备份中..."
backup_true: "§a数据备份完成,备份文件 §e{0}"
import_ing: "§a备份 §e{0} §a正在导入中..."
import_true: "§a备份导入完成"
give_type_false: "§a给予类型不正确"
give_item_null: "§a物品 §e{0} §a不存在"
give_ni_null: "§a服务器没有所需依赖 §eNeigeItems"
give_mm_null: "§a服务器没有所需依赖 §eMythicMobs"
give_sx_null: "§a服务器没有所需依赖 §eSX-Attribute"
give_oa_null: "§a服务器没有所需依赖 §eOriginAttribute"
import_klring_exists_false: "§a请将§e plugins/KLRing/data/soul-space §a下的数据文件放入 §e{0}"
import_klring_exists_error: "§a目录 §e{0} §a为空"
decompose_unlock_false: "§a请返回仓库页面解锁槽位"
decompose_null: "§a此物品无法分解"
decompose_disable: "§a服务器未开启分解功能"
  ```

</details>
