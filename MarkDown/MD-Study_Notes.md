MarkDown Study notes
====================

[Markdown is a lightweight markup language with plain text formatting syntax.][1]
It is designed so that it can be converted to HTML and many other formats using a tool by the same name

[Markdown 语法说明 (简体中文版)][2]

-----

##与HTML兼容

*`Markdown`-->`HTML`-->`Text`*

特殊字符自动转换
>e.g.:
>`&copy;`中的&会被自动转为版权符号&copy;，而`AT&T`仍然保留显示为&

概念
----
###区块元素
- 段落与换行

	Markdown 段落是由 ***`一个或多个连续的文本行`*** 组成，它的前后要有 ***`一个以上`*** 的空行

- 标题

	Setext格式：`==` 与 `--`，输入个数大于1即可

- 区块引用

	`>` 开头
	>特点:
	>
	> 1. 同一段落文字，可以每行都输入`>`，也可只输入第一行
	> 2. 可以嵌套使用引用
	> 3. 引用区块可以使用其他MarkDown语法

- 列表

	无序列表，可以使用符号 `*` `-` `+`后跟 `Space`,
	有序列表，使用数字后跟 `Space`
	
	>特点:
	>
	>1. 项目标记后面则一定要接着至少一个空格或制表符
	>2. 列表项目可以包含多个段落，每个项目下的段落都必须缩进 4 个空格或是 1 个制表符
	>3. 要在列表项目内放进引用，那 `>` 就需要缩进
	>4. 要放代码区块的话，该区块就需要缩进两次，也就是 8 个空格或是 2 个制表符
	>5. 在句点前面加上反斜杠 `\` 可以不产生列表

- 代码区块

	和程序相关的写作或是标签语言原始码通常会有已经排版好的代码区块，通常这些区块我们并不希望它以一般段落文件的方式去排版，而是照原来的样子显示

	>特点：
	>
	>1. 程序相关的写作或是标签语言原始码,按原格式显示
	>2. 简单地缩进 4 个空格或是 1 个制表符
	>3. 代码区块会一直持续到没有缩进的那一行（或是文件结尾）

- 分割线

	你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西,分隔符必须是独立段落，否则与Setext标题冲突

###区段元素
- 链接

	链接辨别标签可以有字母、数字、空白和标点符号，但是并不区分大小写

		行内式：This is [an example](http://example.com/ "Title") inline link.
		参考式：This is [an example] [id] reference-style link.
		
		[id]: http://example.com/  "Optional Title Here"可以写在*.md文本任意位置
		
		隐式链接：[Google][]
		[Google]: http://google.com/，直接用"[]"中的名称来作为[id]使用，可以放在任何位置

		自动链接:<http://example.com/>,直接显示链接本身

- 强调

	星号（*）和底线（_）作为标记强调字词的符号，
	一 * 斜体、
	二 * 加粗黑体、
	三 * 斜体加粗黑体

- 代码

	要标记一小段行内代码，你可以用反引号把它包起来 `` ` ``, 如果想要显示反引号，可以前后各两个包包起来

		A single backtick in a code span: `` ` ``

- 图片

	Markdown 使用一种和链接很相似的语法来标记图片，同样也允许两种样式

		行内式: ![Alt text](/path/to/img.jpg "Optional title")
		参考式: ![Alt text][id]
		
		[id]: url/to/image  "Optional title attribute"

	[![](https://cdn.monetizejs.com/resources/button-32.png)](https://monetizejs.com/authorize?client_id=ESTHdCYOi18iLhhO&summary=true)

		如上图，此种方式显示的直接是图片，Markdown 还没有办法指定图片的宽高，如果你需要的话，可以使用普通的 <img> 标签。
		
		示例图片markdown写法如下	
		[![](https://cdn.monetizejs.com/resources/button-32.png)](https://monetizejs.com/authorize?client_id=ESTHdCYOi18iLhhO&summary=true)
		1.显示图片
		2.直接把图片，嵌入到链接里

- 反斜杠

	Markdown 可以利用反斜杠来插入一些在语法中有其它意义的符号

		\   反斜线
		`   反引号
		*   星号
		_   底线
		{}  花括号
		[]  方括号
		()  括弧
		#   井字号
		+   加号
		-   减号
		.   英文句点
		!   惊叹号
	

使用技巧
---

- 两个`space`+`Enter`会生成<\br>的效果，即强制换行。而直接换行，产生的效果是续写上一行，但中间会有空格生成




[1]: https://en.wikipedia.org/wiki/Markdown	"维基百科"
[2]: http://wowubuntu.com/markdown/index.html	"参考学习blog"
