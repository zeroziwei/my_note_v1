callout 标注块是 obsidian 新增的格式，也被称为**admonitions警告**

表现形式是带颜色的**块引用**，有**标题**、**背景颜色**和icon**图标**。 他极大的丰富了 obsidian 的排版，增加了美观度。

**演示：**

>[!Danger] 类callout标注块演示
>这个就是一个类似的callout块，obsidian中UI和这个略有不同

**语法：**

![[Pasted image 20240629050550.png]]

​
**参数**  
callout可以有很多的样式，替换`[!info]`中的名称

- Note
- Abstract
- Info
- Todo
- Tip
- Success
- Question
- Warning
- Failure
- Danger
- Bug
- Example
- Quote

**使用技巧**

- 在使用callout的时候，注意中间不要有空行，否则会导致空行下面的内容不被包裹。
- 如果是一大段文字，可以先写内容，然后在使用插件 Admonition 插入callout。
- 标题中也支持 markdown 语法


> [!tip]+ 小技巧
> 全选要包裹的内容，调用插件 Admonition 插入 callout，方便不易错



> [!attention]+ Admonition 使用非常简单
> 1. 先选中你要包裹的内容，命令面板呼出，输入callout。
> 2. 弹窗选择样式就结束了。
> 3. 样式、标题、折叠与否去代码里修改，语法在上面
> 
