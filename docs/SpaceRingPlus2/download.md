---
sidebar_position: 3
---

# 插件下载

:::info `1.0.4`

**更新**

1. 重写部分代码，移除类库hutool解决与SimpleLib冲突的问题
2. Cron定时备份改为间隔时间备份(具体留意新配置文件)
3. 配置文件自动更新

此处省略10余项调整

**附件**

[SpaceRingPlus2-1.0.4.jar](https://www.goodmc.cn/plugin/SpaceRingPlus/SpaceRingPlus2-1.0.4.jar)

:::

:::info `1.0.3`

**更新**

1. 修复MySQL数据长度太长无法存入的问题

旧版的数据表需要将表`spaceringplus2_data`字段`data`类型修改为`mediumtext`

:::

:::info `1.0.2`

**更新**

1. 优化give指令物品叠加问题

:::

:::info `1.0.1`

**更新**

1. 修复give指令异常

:::

:::info `1.0.0`

**更新**

1. 基于 Kotlin / Taboolib 重新开发
2. 兼容1.8-1.20
3. 优化数据备份
4. 新增备份数据导入
5. 优化KLRing数据导入
6. 将不同GUI的配置文件独立出来
7. 重写数据管理代码解决MySQL同步和SQLite丢数据
8. 修复玩家无空间戒指give指令物品也会进灵魂空间的问题
9. 不再依赖SimpleLib和fastjson2在内的多个类库，减少依赖冲突
10. 兼容SX-Attribute和OriginAttribute物品库

:::

#### 以下为旧版更新日志,非该插件最新版

:::info`1.0.7`

**更新**

1. 优化JSON存储备份格式
2. 取消打开GUI时的异步操作
3. 兼容SX-Attribute物品库

**附件**

[SpaceRingPlus-1.0.7.jar](https://www.goodmc.cn/plugin/SpaceRingPlus/SpaceRingPlus-1.0.7.jar)

:::

:::info`1.0.6`

**更新**

1. 优化SQLite和MySQL操作代码,增强稳定性

:::

:::info`1.0.5`

**更新**

1. 修复MM怪物Drops获得双倍物品的问题

:::

:::info`1.0.4`

**更新**

1. 修复插件产生错误数据的问题

:::

:::info`1.0.3`

**更新**

1. 优化跨服同步问题
2. 修复无数据的情况掉落物无法进入仓库的问题

:::

:::info`1.0.2`

**更新**

1. 修复上个版本不保存解锁数据的问题

:::

:::info`1.0.1`

**更新**

1. 默认解锁材料可为空
2. 不强制服务器安装PlaceholderAPI和Vault
3. 解锁方案新增默认解锁槽位数量
4. 修复KLRing数据大小写导致数据导入产生的问题

:::

:::info`1.0.0`

插件发售

:::
