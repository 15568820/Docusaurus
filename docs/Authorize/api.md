---
sidebar_position: 1
---

# 接口调用

###  

#### 引用 Maven 依赖

```xml

<dependency>
    <groupId>me.qingshou</groupId>
    <artifactId>SimpleLib</artifactId>
    <version>1.3.1-beta4</version>
    <scope>provided</scope>
</dependency>
```

#### API

```java
/**
 * 注册插件授权
 *
 * @param plugin   插件实例
 * @param pluginId 插件Id
 * @param code     授权码
 */
public void register(Plugin plugin, String pluginId, String code)

/**
 * 注册插件授权
 *
 * @param plugin   插件实例
 * @param pluginId 插件Id
 * @param code     授权码
 * @param runnable 授权成功执行的代码
 */
public final void register(Plugin plugin, String pluginId, String code, Runnable runnable) 
```

#### 示例代码

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';


<Tabs>
<TabItem value="demo1" label="示例1">

```java
import me.qingshou.lib.SimpleLib;
import me.qingshou.lib.anntation.Outsource;
import org.bukkit.plugin.java.JavaPlugin;

public final class AuthorizeDemo extends JavaPlugin {
    // 需要混淆的方法加上该注解
    @Outsource
    public void onEnable() {
        saveDefaultConfig();
        reloadConfig();

        SimpleLib.getAuthorizeManage().register(this, "bc2f905847cf442b9f3abf7bf81245ee", getConfig().getString("config.code"), () -> {
            // Runnable 内写插件授权成功后执行的代码
            getLogger().info("插件正在初始化");
        });
    }

    @Outsource
    public void onDisable() {

    }
}
```

</TabItem>
<TabItem value="demo2" label="示例2">

```java
import me.qingshou.lib.SimpleLib;
import me.qingshou.lib.anntation.Outsource;
import org.bukkit.plugin.java.JavaPlugin;

public final class AuthorizeDemo extends JavaPlugin {
    // 需要混淆的方法加上该注解
    @Outsource
    public void onEnable() {
        saveDefaultConfig();
        reloadConfig();

        SimpleLib.getAuthorizeManage().register(this, "bc2f905847cf442b9f3abf7bf81245ee", getConfig().getString("config.code"));
    }

    @Outsource
    public void onDisable() {

    }
}
```

</TabItem>
</Tabs>

- 完整代码
- [https://github.com/ye0130/AuthorizeDemo](https://github.com/ye0130/AuthorizeDemo)

