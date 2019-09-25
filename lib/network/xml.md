# XML

标签（空格分隔）： 计算机基础

---

Extensible Markup Language，可扩展标记语言，任意标记语言的元语言

* 标记语言：用标签为数据赋予意义的语言
* 可扩展：可随心所欲地创建标签

## 语法

```xml
<?xml version="1.0" encoding="UTF-8"?>
<pet>
  <cat>cat</cat>
  <pig/>
<pet>
```

### 声明

* 开头为xml声明，表明使用的版本和编码方式

```xml
<?xml version="1.0" encoding="UTF-8"?>
```

### 根元素

* 在声明后面，有且只有一个

```xml
<?xml version="1.0" encoding="UTF-8"?>
<root>
  root
</root>
```

### 注释

* 使用<!-- 注释 -->表示注释

```xml
<!-- 这是注释 -->
```

### 标签

* 标签名可随意取，区分大小写，但不能以数字开头，也不能含空格
* 有内容：<标签名>内容</标签名>
* 无内容：<标签名>
* 标签可嵌套，但不能交叉嵌套

```xml
<pet>
  <cat>cat</cat>
  <pig/>
<pet>
```

### 属性

* 可在标签中以属性名="属性值"添加属性

```xml
<cat color="blue">cat</cat>
```

### 文本

* 空格、换行符、制表符都会当成空白字符
* `< > & ' "`要被转义为`&lt; &gt; &amp; &quot; &apos;`
* * `< > & ' "`在<![CDATA[ ... ]]>中不需转义

```xml
<cat>a&amp;b</cat>
<cat><![CDATA[a&b]]></cat>
```
