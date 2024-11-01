
HTML（超文本标记语言）是一种用于创建网页的标记语言。HTML 使用标签（tag）来定义页面内容的结构，比如标题、段落、列表、图片、链接等。以下是一些常用的 HTML 标签和语句。

## HTML 基本结构
每个 HTML 文件通常有一个基本结构，包含 `html`、`head` 和 `body` 标签：


```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>页面标题</title>
</head>
<body>
  <h1>欢迎来到我的网页</h1>
  <p>这是一个简单的 HTML 示例。</p>
</body>
</html>
```

-  **`<head>` 标签**
    - **主要作用**：包含网页的元数据（metadata）和其他设置信息，这些内容不会直接显示在网页中。
    - **常见内容**：
      - **文档标题**：通过 `<title>` 标签设置，显示在浏览器标签上。
      - **字符编码**：通过 `<meta charset="UTF-8">` 指定，确保网页支持多种语言和字符。
      - **描述和关键词**：通过 `<meta name="description">` 和 `<meta name="keywords">` 提供，帮助搜索引擎理解网页内容。
      - **视图设置**：通过 `<meta name="viewport">` 设置页面在移动设备上的显示方式。
      - **样式表和脚本**：使用 `<link>` 引用外部CSS文件，或使用 `<style>` 添加内部CSS样式，影响网页的样式；使用 `<script>` 引用外部JavaScript文件或编写内部JavaScript，添加交互功能。

    **总结**：`<head>` 部分为网页提供信息、设置和资源链接，影响页面的外观和功能，但其内容不会直接显示在页面中。
---
-  **`<body>` 标签**
    - **主要作用**：包含网页的可见内容，即用户在浏览器中直接看到的页面内容。
    - **常见内容**：
      - **文本和图像**：使用 `<p>`、`<h1>` 到 `<h6>`、`<img>` 等标签添加文字和图片。
      - **布局**：使用 `<div>` 和 `<section>` 等标签进行页面布局和内容分区。
      - **交互元素**：包括按钮、表单等，通过 `<button>`、`<form>` 等标签添加用户可操作的元素。
      - **嵌入多媒体**：通过 `<video>`、`<audio>`、`<iframe>` 等标签嵌入视频、音频和其他外部内容。

    **总结**：`<body>` 部分承载网页的实际内容和交互元素，是用户在浏览器中直接看到和操作的页面内容。

- 两者的关系
  - **结构关系**：`<head>` 提供网页的配置信息和资源支持，为 `<body>` 部分提供样式、脚本、描述等设置。
  - **相互依赖**：`<head>` 影响页面在浏览器中的呈现方式，而 `<body>` 则是承载具体内容。两者共同作用构成了完整的网页结构。

## 标签
#### 1. 标题标签
使用 `<h1>` 到 `<h6>` 标签来定义标题，`<h1>` 是最大的标题，`<h6>` 是最小的标题。

```html
<h1>这是一级标题</h1>
<h2>这是二级标题</h2>
<h3>这是三级标题</h3>
```

#### 2. 段落标签
使用 `<p>` 标签定义段落。

```html
<p>这是一个段落。</p>
<p>这是另一个段落。</p>
```
## 嵌入
#### 1. 链接
使用 `<a>` 标签创建超链接，`href` 属性指定链接目标。

```html
<a href="https://www.example.com">访问 Example 网站</a>
```

#### 2. 图片
使用 `<img>` 标签插入图片，`src` 属性指定图片 URL，`alt` 属性用于描述图片。

```html
<img src="image.jpg" alt="图片描述">
```
在HTML中，可以通过不同的标签嵌入视频和文件。以下是一些常见的嵌入方法：

#### 3. 嵌入视频

##### 使用 `<video>` 标签
可以直接在HTML中使用 `<video>` 标签嵌入本地视频或在线视频文件：
```html
<video controls width="600">
  <source src="path/to/your-video.mp4" type="video/mp4"> <!-- MP4视频文件 -->
  <source src="path/to/your-video.ogg" type="video/ogg"> <!-- OGG格式视频文件 -->
  您的浏览器不支持HTML视频播放。
</video>
```
- `controls` 属性：显示播放控件（播放/暂停、音量、全屏等）。
- `width` 属性：设置视频显示宽度。
- `<source>`：定义视频文件的路径和类型。可以设置多个 `<source>` 标签来支持不同格式。

##### 使用嵌入YouTube视频的 `<iframe>` 标签
如果视频在YouTube上，可以使用 `<iframe>` 嵌入：
```html
<iframe width="560" height="315" 
        src="https://www.youtube.com/embed/your_video_id" 
        title="YouTube video player" 
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
        allowfullscreen>
</iframe>
```
- `src`：将 `your_video_id` 替换为YouTube视频的ID。
- `width` 和 `height`：定义视频显示尺寸。
- `allowfullscreen`：允许全屏播放。

#### 4. 嵌入文件

#### 使用 `<iframe>` 嵌入文件
可以使用 `<iframe>` 显示PDF文件、HTML文件或其他网页内容：
```html
<iframe src="path/to/your-file.pdf" width="600" height="500" title="PDF Viewer"></iframe>
```
- `src`：设置文件的路径（例如PDF文件）。
- `width` 和 `height`：设置显示区域的大小。

#### 使用 `<embed>` 标签嵌入文件
`<embed>` 标签也可以用于嵌入PDF文件或其他文档：
```html
<embed src="path/to/your-file.pdf" width="600" height="500" type="application/pdf">
```
- `src`：指定文件路径。
- `type`：定义文件类型，例如PDF文件使用 `application/pdf`。

#### 使用 `<a>` 标签下载文件
可以使用链接直接提供文件的下载：
```html
<a href="path/to/your-file.pdf" download="filename.pdf">下载PDF文件</a>
```
- `href`：指定文件路径。
- `download`：设置下载文件的默认名称（可选）。

## 列表和表格
#### 1.无序列表
使用 `<ul>` 和 `<li>` 标签创建无序列表。

```html
<ul>
  <li>项目 1</li>
  <li>项目 2</li>
  <li>项目 3</li>
</ul>
```

#### 2.有序列表
使用 `<ol>` 和 `<li>` 标签创建有序列表。

```html
<ol>
  <li>第一步</li>
  <li>第二步</li>
  <li>第三步</li>
</ol>
```

#### 3.表格
使用 `<table>`、`<tr>`、`<td>` 和 `<th>` 标签创建表格。

```html
<table>
  <tr>
    <th>姓名</th>
    <th>年龄</th>
  </tr>
  <tr>
    <td>小明</td>
    <td>20</td>
  </tr>
  <tr>
    <td>小红</td>
    <td>22</td>
  </tr>
</table>
```

#### 4. 表单
使用 `<form>` 标签创建表单，包含 `<input>`、`<label>`、`<button>` 等标签。

```html
<form action="/submit" method="post">
  <label for="name">姓名：</label>
  <input type="text" id="name" name="name">
  
  <label for="email">邮箱：</label>
  <input type="email" id="email" name="email">
  
  <button type="submit">提交</button>
</form>
```

## 分割线
使用 `<hr>` 标签创建水平分割线。

```html
<p>这是第一段。</p>
<hr>
<p>这是第二段。</p>
```
## 注释、强调与文字颜色
#### 1. 注释
使用 `<!-- ... -->` 来添加注释，注释内容不会显示在网页上。

```html
<!-- 这是一个注释 -->
<p>这是一个段落。</p>
```

#### 2. 强调和斜体、文字颜色、样式
使用 `<strong>` 或 `<b>` 标签使文本加粗，使用 `<em>` 或 `<i>` 标签使文本斜体。

```html
<p>这是 <strong>加粗</strong> 的文字。</p>
<p>这是 <em>斜体</em> 的文字。</p>

<font color="blue">文字</font>  
<span style="color: orange;">文字</span>

<div style="text-align: center;">
  这是居中的文字
</div>


```
## 样式
#### 1. 内联样式
使用 `style` 属性为标签添加内联样式。

```html
<p style="color: blue; font-size: 20px;">这是蓝色的文字。</p>
<summary style="display: inline; color: red;">甘特图>><span></summary>
<!-- display:inline在summary里会取消展开箭头，并且行内元素不会强制换行 -->
```

#### 2. 内部和外部样式
HTML 支持使用 `<style>` 标签添加内部样式，或使用 `<link>` 标签引用外部样式表。

##### 内部样式
```html
<style>
  body {
    background-color: lightgray;
  }
  h1 {
    color: blue;
  }
</style>
```

##### 外部样式
```html
<link rel="stylesheet" href="styles.css">
```
## 脚本
#### JavaScript 脚本
使用 `<script>` 标签添加 JavaScript 脚本，可以直接嵌入或引用外部脚本文件。

#### 内联 JavaScript
```html
<script>
  alert("欢迎来到我的网页！");
</script>
```

#### 外部 JavaScript
```html
<script src="script.js"></script>
```

## HTML实例
```html
<html lang="en"> <!-- 声明HTML文档的语言为英文 -->
<head>
  <meta charset="UTF-8"> <!-- 设置文档字符编码为UTF-8，确保兼容大部分语言和符号 -->
  <title>Document</title> <!-- 设置网页的标题，在浏览器标签中显示 -->
  <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" /> <!-- 启用IE的最新渲染模式，并兼容Chrome Frame -->
  <meta name="description" content="Description"> <!-- 设置网页描述内容，有助于SEO优化 -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0"> <!-- 为移动设备优化视图设置，确保页面在不同屏幕尺寸下自适应 -->
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css"> <!-- 引用Docsify的Vue风格主题CSS文件，使文档页面具有Vue主题的样式 -->
</head>

<body>
  <div id="app"></div> <!-- 页面内容的容器，通过Docsify来渲染文档内容 -->

  <!-- 配置Docsify选项 -->
  <script>
    window.$docsify = {
      name: '',                  // 设置文档项目的名称，将显示在页面顶部导航栏（这里为空）
      repo: '',                  // 设置项目的GitHub仓库地址，导航栏中会出现一个跳转按钮（这里为空）
      loadSidebar: true,         // 启用侧边栏（通常由_sidebar.md生成）
      subMaxLevel: 3,            // 指定显示的侧边栏标题层级（设置为3级）
      loadNavbar: true,          // 启用顶栏（通常由_navbar.md生成）
      coverpage: true,           // 启用封面页
      onlyCover: true            // 如果为true，初次加载时只显示封面页内容
    }
  </script>

  <!-- 引入Docsify库 -->
  <script src="//cdn.jsdelivr.net/npm/docsify@4"></script> <!-- 引入Docsify库的JavaScript文件，使页面成为Docsify应用 -->

  <!-- 引入KaTeX库及依赖，用于渲染数学公式 -->
  <script src="//cdn.jsdelivr.net/npm/katex@latest/dist/katex.min.js"></script> <!-- 引入KaTeX库 -->
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/katex@latest/dist/katex.min.css" /> <!-- 引入KaTeX的CSS文件 -->
  <script src="//cdn.jsdelivr.net/npm/marked@4"></script> <!-- 引入Marked库，将Markdown转换为HTML -->
  
  <!-- 引入docsify-katex插件，支持Docsify中渲染数学公式 -->
  <script src="//cdn.jsdelivr.net/npm/docsify-katex@latest/dist/docsify-katex.js"></script>
</body>
</html>
```

在 HTML 中，文字的排版方式有多种，可以通过 HTML 标签和 CSS 样式来控制。以下是常用的文字排版方式：

## 文字排版方式
#### 1. **对齐方式**

通过 CSS 的 `text-align` 属性可以实现文字的对齐方式：

- **左对齐**（默认）：`text-align: left;`
- **右对齐**：`text-align: right;`
- **居中对齐**：`text-align: center;`
- **两端对齐**：`text-align: justify;`

示例：

```html
<p style="text-align: center;">居中的文字</p>
```

#### 2. **字体样式**

使用 CSS 的 `font-family`、`font-size`、`font-weight` 和 `font-style` 等属性设置字体样式：

- **字体**：`font-family: Arial, sans-serif;`
- **字体大小**：`font-size: 16px;`
- **加粗**：`font-weight: bold;`
- **斜体**：`font-style: italic;`

示例：

```html
<p style="font-family: Arial; font-size: 18px; font-weight: bold; font-style: italic;">
  这是设置了字体样式的文字
</p>
```

#### 3. **行高和字间距**

- **行高**：`line-height` 用于控制行间距，一般设置为 1.5 或 1.6。
- **字间距**：`letter-spacing` 用于控制字符之间的间距。
- **单词间距**：`word-spacing` 用于控制单词之间的间距。

示例：

```html
<p style="line-height: 1.5; letter-spacing: 1px; word-spacing: 2px;">
  设置行高、字间距和单词间距的文字
</p>
```

#### 4. **文本装饰**

通过 `text-decoration` 属性，可以对文字添加下划线、删除线或上划线：

- **下划线**：`text-decoration: underline;`
- **删除线**：`text-decoration: line-through;`
- **上划线**：`text-decoration: overline;`

示例：

```html
<p style="text-decoration: underline;">下划线文字</p>
<p style="text-decoration: line-through;">删除线文字</p>
```

#### 5. **文本缩进**

可以使用 `text-indent` 设置段落的首行缩进：

- **首行缩进**：`text-indent: 2em;`

```html
<p style="text-indent: 2em;">
  这是带有首行缩进的段落。
</p>
```

#### 6. **文字颜色**

使用 `color` 属性设置文字颜色，可以使用色名、十六进制颜色值或 RGB 值：

```html
<p style="color: #ff5733;">带有颜色的文字</p>
```

#### 7. **文字转换**

使用 `text-transform` 控制文字的大小写：

- **全部大写**：`text-transform: uppercase;`
- **全部小写**：`text-transform: lowercase;`
- **首字母大写**：`text-transform: capitalize;`

```html
<p style="text-transform: uppercase;">全部大写的文字</p>
```

#### 8. **换行和空白控制**

使用 `white-space` 控制文本换行和空白：

- **自动换行**：`white-space: normal;`
- **不换行**：`white-space: nowrap;`
- **保留空格和换行**：`white-space: pre;`

```html
<p style="white-space: pre;">
  这是     带有多重空格和换行的文本。
</p>
```

#### 9. **浮动和悬挂**

在布局中使用 `float` 和 `position` 实现文字的浮动效果或悬挂效果。

- **浮动**：`float: left;` 或 `float: right;` 用于文字环绕图像。
- **悬挂**：利用 `position: relative;` 和 `position: absolute;` 可以实现悬挂样式。

#### 综合示例

```html
<p style="text-align: justify; font-family: Arial; font-size: 16px; line-height: 1.6; color: #333; text-indent: 2em;">
  这是一个综合排版示例，包含了左对齐、行高、颜色和首行缩进的样式。
</p>
```

通过这些排版方式，可以灵活调整文字的显示效果，使网页内容更加清晰美观。
#### 总结
以上是常见的 HTML 语句和标签，通过这些基本的标签，可以构建出简单的网页。HTML 与 CSS、JavaScript 结合使用可以制作更加复杂和交互性强的网页。

## 标签元素和属性

### 标签元素

在 HTML 中，`<div>`、`<span>`、`<li>`、`<ul>`、`<p>` 等标签都是用来组织和格式化网页内容的，它们各自有不同的用途和特性。下面是它们的作用及关系：

#### 1. **块级元素 vs. 内联元素**
   - **块级元素**：在页面上独占一行，占据父容器的全部宽度。常见的块级元素包括 `<div>`、`<ul>`、`<li>`、`<p>` 等。
   - **内联元素**：只占据它所需要的宽度，不会换行，通常用于嵌入在块级元素中。常见的内联元素包括 `<span>`、`<a>`、`<img>` 等。

#### 2. 元素的具体用途
   - **`<div>`**（Division）：一个通用的块级容器，用于将内容分组，没有语义。主要用于布局，常用来包裹其他元素。
   - **`<span>`**：一个通用的内联容器，用于包裹文本或其他内联元素，没有语义。通常用于局部样式或标记一小段文字。
   - **`<ul>`**（Unordered List）：无序列表的容器，用于表示列表内容。通常配合 `<li>` 元素来显示项目符号列表。
   - **`<li>`**（List Item）：列表项，必须包含在 `<ul>` 或 `<ol>` 标签内，用于表示列表中的每一项内容。
   - **`<p>`**（Paragraph）：表示一个段落，是块级元素。通常用于段落文本，每个 `<p>` 都会在页面上独占一行。

#### 3. 它们的嵌套关系和用法
这些元素通常可以相互嵌套使用，以创建复杂的布局或结构。以下是一些常见的用法和嵌套关系：

##### 例 1：`<div>` 包含块级和内联元素
```html
<div>
    <p>这是一个段落。</p>
    <span>这是一个内联的 <span style="color: red;">红色文本</span>。</span>
</div>
```
在这个例子中：
- `<div>` 包含了一个块级元素 `<p>` 和一个内联元素 `<span>`。
- `<p>` 独占一行，而 `<span>` 只是占据它所需的宽度。

##### 例 2：列表中的结构
```html
<ul>
    <li>第一项</li>
    <li>第二项
        <ul>
            <li>第二项的子项 1</li>
            <li>第二项的子项 2</li>
        </ul>
    </li>
    <li>第三项</li>
</ul>
```
在这个例子中：
- `<ul>` 是一个无序列表的容器，包含多个 `<li>`。
- `<li>` 可以嵌套 `<ul>`，从而实现多级列表结构。

##### 例 3：布局中的 `<div>` 和 `<span>`
```html
<div class="container">
    <div class="header">标题</div>
    <div class="content">
        <p>这是一个段落。</p>
        <span>这是一个内联的标记。</span>
    </div>
    <div class="footer">页脚信息</div>
</div>
```
在这个例子中：
- `<div class="container">` 作为主容器，包含了多个块级 `<div>`。
- `<span>` 和 `<p>` 分别用于内容中的局部样式和段落。

#### 4. 选择何时使用 `<div>`、`<span>`、`<ul>` 等
- **使用 `<div>`**：当需要布局或将多个元素分组时，适合使用 `<div>`。通常在使用 CSS 布局时，`<div>` 是非常常见的容器。
- **使用 `<span>`**：当只想给一小段文本或内联内容加样式时适合使用 `<span>`，尤其是在段落或行内内容中。
- **使用 `<ul>` 和 `<li>`**：当需要展示项目列表时使用 `<ul>` 和 `<li>`。如果列表有顺序，则可以使用 `<ol>`（有序列表）。
- **使用 `<p>`**：当需要段落文本时使用 `<p>`，它在语义上表示一个完整的段落。

#### 总结
- `<div>` 和 `<span>` 都是无语义的元素，`<div>` 是块级，`<span>` 是内联，适合用来包裹内容并应用样式。
- `<ul>` 和 `<li>` 是语义化的元素，适合用于列表结构。
- `<p>` 表示段落，是块级元素。

合理地选择和嵌套这些元素，可以创建出丰富且语义化的网页结构。



### 标签属性

在 HTML 和 Web 开发中，`class`、`id`、`style`、`script` 等是用于定义元素样式、行为和标识的重要属性或标签。

#### 1. `class` 属性
- **定义**：`class` 是 HTML 元素的一个属性，用于指定一个或多个类名。
- **作用**：用于 CSS 样式和 JavaScript 脚本的选择，便于批量管理多个具有相同类名的元素。
- **特点**：
  - 可以为一个元素指定多个类名，用空格分隔。
  - 可以在同一个页面中多次使用相同的类名。
- **示例**：

  ```html
  <div class="box red">内容</div>
  <div class="box blue">内容</div>
  ```

  在上面的例子中，`box` 和 `red` 是类名，可以通过 CSS 对它们进行样式设置。

#### 2. `id` 属性
- **定义**：`id` 是 HTML 元素的一个属性，用于给元素分配一个唯一的标识符。
- **作用**：用于唯一标识一个元素，在 CSS 和 JavaScript 中都可以通过 `id` 精确地选中该元素。
- **特点**：
  - 在一个页面中，每个 `id` 必须是唯一的（不能重复）。
  - 通常用于特定的、独立的元素，而不是批量应用样式的情况。
- **示例**：

  ```html
  <div id="header">这是头部</div>
  <div id="footer">这是尾部</div>
  ```

  在 CSS 或 JavaScript 中，可以通过 `#header` 和 `#footer` 精确选中这些元素。

#### 3. `style` 属性
- **定义**：`style` 是 HTML 元素的一个属性，用于直接在元素内嵌入 CSS 样式。
- **作用**：为特定元素指定样式，通常用于快速定义样式或覆盖全局样式。
- **特点**：
  - 适合于局部样式的定义，不推荐大规模使用（应优先使用外部或内嵌 CSS）。
  - 样式写在 `style` 属性内，作为内联样式。
- **示例**：

  ```html
  <div style="color: red; font-size: 18px;">红色文本</div>
  ```

  上述代码将 `div` 元素的文字颜色设置为红色，字体大小设置为 18px。

#### 4. `<script>` 标签
- **定义**：`<script>` 标签用于在 HTML 文档中嵌入 JavaScript 代码。
- **作用**：可以用来添加 JavaScript 脚本，以实现页面的动态行为。
- **特点**：
  - 可以直接在 HTML 文档内编写 JavaScript 代码，或通过 `src` 属性引入外部脚本文件。
  - `<script>` 标签通常放在页面的末尾或 `<head>` 中，以便在页面加载完成后执行。
- **示例**：

  内联 JavaScript：

  ```html
  <script>
      console.log("Hello, World!");
  </script>
  ```

  引用外部 JavaScript 文件：

  ```html
  <script src="script.js"></script>
  ```

#### 5. `<link>` 标签
- **定义**：`<link>` 标签用于将外部资源链接到 HTML 文档中，最常用于引入外部 CSS 文件。
- **作用**：加载外部样式表或其他资源，以便在页面中应用。
- **特点**：
  - 常用于引入 CSS 文件，使页面的样式与内容分离。
  - `<link>` 标签放在 `<head>` 中。
- **示例**：

  ```html
  <link rel="stylesheet" href="styles.css">
  ```

#### 6. `<style>` 标签
- **定义**：`<style>` 标签用于在 HTML 文档中嵌入 CSS 样式。
- **作用**：可以在 HTML 页面中直接写 CSS 样式，通常用于局部样式或特定页面的样式。
- **特点**：
  - 一般放置在 `<head>` 部分。
  - 适用于页面级的样式，避免内联 `style` 属性造成的代码冗长。
- **示例**：

  ```html
  <style>
      .header { color: blue; font-size: 20px; }
  </style>
  ```

#### 7. `data-*` 自定义数据属性
- **定义**：`data-*` 是一种 HTML 自定义属性，用于在元素中存储额外的、自定义的数据。
- **作用**：可以存储与页面或应用逻辑相关的数据，并且不会被展示出来。
- **特点**：
  - 常用于在 JavaScript 中传递数据，以便在页面中动态显示。
  - 以 `data-` 开头，可以自定义任何名称的属性。
- **示例**：

  ```html
  <div data-user-id="12345" data-role="admin">用户名</div>
  ```

  在 JavaScript 中可以通过 `dataset` 访问：

  ```javascript
  let userId = document.querySelector('div').dataset.userId;
  console.log(userId);  // 输出 "12345"
  ```

#### 总结
- **`class`**：用于给多个元素分配相同的类名，便于批量应用样式或选择元素。
- **`id`**：唯一标识某个元素，适合特定的独立元素。
- **`style`**：为元素添加内联样式，用于快速设置或覆盖样式。
- **`<script>`**：嵌入或引入 JavaScript 脚本，使页面具备动态交互功能。
- **`<link>`**：引入外部资源，主要用于外部 CSS 文件。
- **`<style>`**：嵌入 CSS 样式，适用于页面范围的样式定义。
- **`data-*`**：用于存储自定义数据，便于 JavaScript 使用和交互。

这些属性和标签是网页开发的基本构成块，帮助开发者创建结构化、有样式、具有交互性的网页。