谢谢你想要帮我们完善资源地图。


由于所有这些地图都位于GitHub上，因此更改或添加新内容意味着要在GitHub上添加内容。幸运的是，这些地图在代码中的表现方式非常简单，因此添加和更改内容应该非常简单。

不过，你所做的更改应该遵循我们的准则，我们的准则专注于为探究的所有课题提供最有效的学习途径。

### 指引

- 所有 **地图必须感觉非常相似**.
- 他们通常都有一个指向维基百科文章的 **主节点**。 这个主节点通常有一个类似 reddit ， stack exchange community 或者 附加一个 GitHub 项目列表。 对于软件项目，它也可以有一个跟课题相关的 GitHub 仓库。 到这里你已经有了一个 "基础节点"，它提供了逐步探究该课题最有效的途径。
- 学习资源可以是任何形式的。书籍，课程，视频，互动教程等等。**资源的流行程度并不重要，重要的是它能很好地帮我们理解课题并且是完全免费的。** 当然某些书籍不是免费的，我们应该提供Goodreads页面。这些步骤表示资源被涵盖的理想顺序。通常，同一步骤可能涉及多个资源。这并没关系。
- 除了"基础节点"，**你可以提供额外的的资料**来帮助学习课题内容。你可以添加一些跟课题相关的有趣的链接。一些示例可能包括**帮助节点**，备忘单或摘要。有趣的节点**，有各种有趣的链接，如会谈或文章。一个**工具节点**，包含与该主题相关的各种工具。带有与该主题相关的文章列表的**文章节点**。这里可以包含的资源也应该是高质量的并且与该主题相关。对于文章和会谈，最好在文章，会谈的发行年份前面加上前缀。为了可读性，我们对年份进行了缩写，因此以“17：”为前缀的文章意味着文章是在2017年撰写的。
- **从基础节点出发，地图的分支延伸出了新的课题（通常是其他地图）**。地图分支需要十分明了。**比如 '编程语言' 需要在 '编程' 课题下面。** 我们知道知识最终是一个图表，而不是一个分支树，我们试图尽可能展示这一切的相互联系。

### 语法
所有地图都以 JSON 格式进行存储，非常便于编辑。

<pre>
{
  "title": "life---hobbies",
  "description": "A hobby is a regular activity that is done for enjoyment, typically during one's leisure time.",
  "tag": "hobbies",
  "connections": [
    ...
  ],
  "key": "hobbies",
  "nodes": [
    ...
  ]
}
</pre>

这是一个地图的顶级部分，在这里一些元信息需要说明，比如：

- **title：** 知识图谱的路径。
- **description (可选):** 当分享地图时，这里会展示课题的简短描述。
- **tag (可选):** 自定义的检索标签，优先级高于地图名字。举例来说, 以 `R` 命名的地图，有一个 `R programming language` 标签。

然后还有一些其他信息直接用于渲染地图 :

- **nodes:** a list of nodes with their respective name and link to resources.
- **connections:** a list with the connections between all nodes.

#### Nodes
这里是节点的例子：

<pre>
{
  "text": "python",
  "url": "http://www.wikiwand.com/en/Python_(programming_language)",
  "fx": -13.916222252976013,
  "fy": -659.1641376795345,
  "category": "wiki",
  "note": "",
  "nodes": []
}
</pre>

可能的属性列表:

- **text:** 展示在节点上的文本。
- **url:** 节点绑定的链接地址。
- **category:** 类别用来生成 emoji。
- **note:** 当鼠标悬停在节点时会显示。
- **fx and fy (optional):** 节点的坐标（你可能不想指定这些节点，因为目前获取它们相当复杂）。
- **nodes:** 与节点具有相同结构的子节点的列表（子节点是列在节点旁边的那些资源，例如基本节点总是具有子节点）。

#### Connections
这是一个 connection 的示例:

<pre>
{
  "source": "python",
  "target": "basics",
  "curve": {
    "x": -43.5535,
    "y": 299.545
  }
}
</pre>

这是可能的属性列表:

- **source:** 连接开始处的节点的文本。
- **target:** 连接结束处的节点的文本。
- **curve (可选):** 用于生成连接曲线的坐标（与上述坐标相同的 story，可以将其保留为“曲线”：{'{}'}`）。

### 有困难?
前往我们的 [Slack 小组](https://knowledge-map.slack.com/shared_invite/MTgxNTYzMjIzNjM5LTE0OTQzMzA4MDAtYzY1YWY0ZDc0NQ) ，我们很乐意帮助你！
