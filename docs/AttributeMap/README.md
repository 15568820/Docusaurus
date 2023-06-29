# AttributeMap

### **适用版本**

> 1.12.2

### **依赖插件**

> - 必要: SimpleLib (群内下载)

### **插件介绍**

> - 相当于自定义属性
> - 如果定义一个属性映射 “体质”,其属性为生命值:100和防御力:100
> - 玩家拥有体质:100 相当于拥有生命值:10000和防御力:10000
> - 支持小数点

### **配置文件**

```yaml
Config:
# 使用必看
# 请在SX的Config.yml的AttributePriority下添加参数 AttributeMap: 数值(自己按规律填数值)

# 您的授权码
Code: "IKUN-JNTM-SZ666-SUSHAN"
# 属性映射列表,可自行按照格式添加
AttributeList:
  # 变量 %sx_Test%
  Test:
    # 武器带有 测试属性: 100 这样的格式即可生效属性
    Name: "测试属性"
    # 映射的属性
    Attribute:
      生命上限: 150.0
      攻击力: 100.0
  # 变量 %sx_Test2%
  Test2:
    # 武器带有 属性测试: 100 这样的格式即可生效属性
    Name: "属性测试"
    # 映射的属性
    Attribute:
      生命上限: 200.0
      攻击力: 200.0
Message:
  reload: "§a配置文件重载成功"
  permission_false: "§a您的权限不够"
```