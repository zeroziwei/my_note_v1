## 为什么需要查询(why)
## 从哪里查(where)

from：指定查询的地方，

- 如果是文件夹，格式固定为 `"文件夹"`，英文双引号里面是文件夹名字，双引号一定要有。
- 如果是标签，格式固定为`#标签名`，英文的`#`号加上标签名字，英文的`#`号一定要有。
- 如果同时查询两个条件，可以用`and`连接起来，表示同时具备。
- 如果从两个条件中任一匹配一个，可以用`or`连接起来，表示或者，选择其中一个。

## 查什么(what)

![[Pasted image 20240629032610.png]]
### 隐式字段 

####  file.文件隐式字段

- `file.name`: 文件标题（一个字符串）.
- `file.folder`: 这个文件所属的文件夹的路径.
- `file.path`: 完整的文件路径（一个字符串）.
- `file.ext`: 文件类型的扩展名；一般为'.md'（字符串）.
- `file.link`: 通往该文件的链接（一个链接）
- `file.size`: 文件的大小（以字节为单位）（一个数字）.
- `file.ctime`: 该文件的创建日期（一个日期+时间）
- `file.cday`: 文件创建的日期（只是一个日期）.
- `file.mtime`: 文件最后被修改的日期（一个日期+时间）。.
- `file.mday`: 文件最后被修改的日期（只是一个日期）。.
- `file.tags`: 笔记中所有独特标签的一个数组. 小标签按每个级别进行细分, so `#Tag/1/A` 将被存储在数组中，作为 `[#Tag, #Tag/1, #Tag/1/A]`.
- `file.etags`: 注释中所有显式标签的数组; unlike `file.tags`, 不包括子标签.
- `file.inlinks`: 该文件的所有传入链接的数组.
- `file.outlinks`: 该文件中所有外链的数组.
- `file.aliases`: 笔记中所有别名的一个数组.
- `file.tasks`: 一个包含所有任务的数组 (I.e., `- [ ] blah blah blah`) 在这个文件中。
- `file.lists`: 文件中所有列表元素的数组（包括任务）；这些元素是有效的任务，可以在任务视图中呈现。.
- `file.frontmatter`: 包含所有frontmatter的原始值；主要用于检查frontmatter的原始值或动态地列出前题的 keys 键值(字段)。

如果文件的标题内有一个日期（形式为 `yyyy-mm-dd` 或 `yyyymmdd`），或有一个Date字段/inline字段，它也有以下属性。

- `file.day`: 与文件标题相关的明确日期. 如果你使用obsidian核心插件 "Starred Files"，以下元数据也是可用的。
- `file.starred`: 如果这个文件已经被 "stars " obsidian插件加了星号。

#### task.待办隐式字段

- `status`: 该任务的完成状态，由`[]`括号内的字符决定。一般来说，空格`" "`表示未完成的任务，X`"X"`表示完成的任务，但允许支持其他任务状态的插件。
- `checked`: 该任务是否以任何方式被检查过（即它的状态不是未完成/空的）。.
- `completed`: 这个_具体的_任务是否已经完成；这不考虑任何子任务的完成/未完成情况。如果一项任务被标记为 "X"，则明确视为 "完成"。.
- `fullyCompleted`: Whether or not this task and **all** of its subtasks are completed.
- `text`: 这项任务的文本.
- `line`: 该任务显示的行.
- `lineCount`: 这项任务所占的 markdown 行数.
- `path`: 该任务所在文件的完整路径.
- `section`: 该任务包含的章节链接.
- `tags`: 文本任务内的任何标签。
- `outlinks`: 本任务中定义的任何链接.
- `link`: 通往该任务附近最近的可链接区块的链接；对于建立通往该任务的链接很有用。.
- `children`: 该任务的任何子任务或子清单.
- `task`: 如果为真，这是一个任务；否则，它是一个普通的列表元素.
- `completion`: 一项任务完成的日期; set by `completion...` or [shorthand syntaxopen in new window](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-tasks/#field-shorthands).
- `due`: 任务到期的日期，如果它有一个。. Set by `due...` or [shorthand syntaxopen in new window](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-tasks/#field-shorthands).
- `created`: 一个任务的创建日期; set by `created...` or [shorthand syntaxopen in new window](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-tasks/#field-shorthands).
- `start`: 一个任务可以开始的日期; set by `start...` or [shorthand syntaxopen in new window](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-tasks/#field-shorthands).
- `scheduled`: The date a task is scheduled to work on; set by `scheduled...` or [shorthand syntaxopen in new window](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-tasks/#field-shorthands).
- `annotated`: 如果任务有任何自定义注解，则为真，否则为假.
- `parent`: 这个任务上面的任务的行号，如果存在的话；如果这是一个根级任务，则为空。.
- `blockId`: 该任务/列表元素的块ID, if one has been defined with the `^blockId` syntax; otherwise null.
