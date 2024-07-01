## Where 过滤器-查函数

### 1.  contains() 包含函数

- 对于对象，检查该对象是否有具有给定名称的键
- 对于列表，检查是否有任何数组元素等于给定值
- 对于字符串，检查给定值是否为子字符串

```
contains(file.name, "咖啡豆") = true
# 检查对象 file.name ，包含“咖啡豆”，就返回结果为 真
```
### 2. date(any) 日期函数

从提供的字符串、日期或链接对象中分析日期（如果可能），否则返回nul

```
date("2020-04-18") 
# 日期对象代表 2020年4月18日

date([[2021-04-16]])
# 给定页面的日期对象，参考file.day
```
### 3.  dur(any) 从字符串解析时间

从提供的字符串或持续时间分析**持续时间**，失败时返回null

```
dur(8 minutes)
# 8分钟

dur("8 minutes, 4 seconds")
# 8分4秒

dur(dur(8 minutes))
# dur(8 minutes) = <8 minutes>
```

### 4. 实战2:where带2个函数查询

```
list
from ""
WHERE file.mtime >= date(today) - dur(7 day)
sort file.mtime desc
```

```
table without id
	file.link as 文件名,
	file.folder as "文件夹",
	file.mtime as 修改时间
from "" and -#obsidian
WHERE file.mtime >= date(today) - dur(7 day)
sort file.mtime desc
limit 20
```

##  limit限制显示数量

当你查询的数据过多的时候，可能不想显示太多的内容。那么我们可以控制显示数据的数量，比如只显示10个。语法简单，不多赘述
