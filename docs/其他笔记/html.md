
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
### 1. 标题标签
使用 `<h1>` 到 `<h6>` 标签来定义标题，`<h1>` 是最大的标题，`<h6>` 是最小的标题。

```html
<h1>这是一级标题</h1>
<h2>这是二级标题</h2>
<h3>这是三级标题</h3>
```

### 2. 段落标签
使用 `<p>` 标签定义段落。

```html
<p>这是一个段落。</p>
<p>这是另一个段落。</p>
```
## 嵌入
### 1. 链接
使用 `<a>` 标签创建超链接，`href` 属性指定链接目标。

```html
<a href="https://www.example.com">访问 Example 网站</a>
```

### 2. 图片
使用 `<img>` 标签插入图片，`src` 属性指定图片 URL，`alt` 属性用于描述图片。

```html
<img src="image.jpg" alt="图片描述">
```
在HTML中，可以通过不同的标签嵌入视频和文件。以下是一些常见的嵌入方法：

### 3. 嵌入视频

#### 使用 `<video>` 标签
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

#### 使用嵌入YouTube视频的 `<iframe>` 标签
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

### 4. 嵌入文件

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
### 1.无序列表
使用 `<ul>` 和 `<li>` 标签创建无序列表。

```html
<ul>
  <li>项目 1</li>
  <li>项目 2</li>
  <li>项目 3</li>
</ul>
```

### 2.有序列表
使用 `<ol>` 和 `<li>` 标签创建有序列表。

```html
<ol>
  <li>第一步</li>
  <li>第二步</li>
  <li>第三步</li>
</ol>
```

### 3.表格
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

### 4. 表单
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
### 1. 注释
使用 `<!-- ... -->` 来添加注释，注释内容不会显示在网页上。

```html
<!-- 这是一个注释 -->
<p>这是一个段落。</p>
```

### 2. 强调和斜体、文字颜色、样式
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
### 1. 内联样式
使用 `style` 属性为标签添加内联样式。

```html
<p style="color: blue; font-size: 20px;">这是蓝色的文字。</p>
<summary style="display: inline; color: red;">甘特图>><span></summary>
<!-- display:inline在summary里会取消展开箭头，并且行内元素不会强制换行 -->
```

### 2. 内部和外部样式
HTML 支持使用 `<style>` 标签添加内部样式，或使用 `<link>` 标签引用外部样式表。

#### 内部样式
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

#### 外部样式
```html
<link rel="stylesheet" href="styles.css">
```
## 脚本
### JavaScript 脚本
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
### 1. **对齐方式**

通过 CSS 的 `text-align` 属性可以实现文字的对齐方式：

- **左对齐**（默认）：`text-align: left;`
- **右对齐**：`text-align: right;`
- **居中对齐**：`text-align: center;`
- **两端对齐**：`text-align: justify;`

示例：

```html
<p style="text-align: center;">居中的文字</p>
```

### 2. **字体样式**

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

### 3. **行高和字间距**

- **行高**：`line-height` 用于控制行间距，一般设置为 1.5 或 1.6。
- **字间距**：`letter-spacing` 用于控制字符之间的间距。
- **单词间距**：`word-spacing` 用于控制单词之间的间距。

示例：

```html
<p style="line-height: 1.5; letter-spacing: 1px; word-spacing: 2px;">
  设置行高、字间距和单词间距的文字
</p>
```

### 4. **文本装饰**

通过 `text-decoration` 属性，可以对文字添加下划线、删除线或上划线：

- **下划线**：`text-decoration: underline;`
- **删除线**：`text-decoration: line-through;`
- **上划线**：`text-decoration: overline;`

示例：

```html
<p style="text-decoration: underline;">下划线文字</p>
<p style="text-decoration: line-through;">删除线文字</p>
```

### 5. **文本缩进**

可以使用 `text-indent` 设置段落的首行缩进：

- **首行缩进**：`text-indent: 2em;`

```html
<p style="text-indent: 2em;">
  这是带有首行缩进的段落。
</p>
```

### 6. **文字颜色**

使用 `color` 属性设置文字颜色，可以使用色名、十六进制颜色值或 RGB 值：

```html
<p style="color: #ff5733;">带有颜色的文字</p>
```

### 7. **文字转换**

使用 `text-transform` 控制文字的大小写：

- **全部大写**：`text-transform: uppercase;`
- **全部小写**：`text-transform: lowercase;`
- **首字母大写**：`text-transform: capitalize;`

```html
<p style="text-transform: uppercase;">全部大写的文字</p>
```

### 8. **换行和空白控制**

使用 `white-space` 控制文本换行和空白：

- **自动换行**：`white-space: normal;`
- **不换行**：`white-space: nowrap;`
- **保留空格和换行**：`white-space: pre;`

```html
<p style="white-space: pre;">
  这是     带有多重空格和换行的文本。
</p>
```

### 9. **浮动和悬挂**

在布局中使用 `float` 和 `position` 实现文字的浮动效果或悬挂效果。

- **浮动**：`float: left;` 或 `float: right;` 用于文字环绕图像。
- **悬挂**：利用 `position: relative;` 和 `position: absolute;` 可以实现悬挂样式。

### 综合示例

```html
<p style="text-align: justify; font-family: Arial; font-size: 16px; line-height: 1.6; color: #333; text-indent: 2em;">
  这是一个综合排版示例，包含了左对齐、行高、颜色和首行缩进的样式。
</p>
```

通过这些排版方式，可以灵活调整文字的显示效果，使网页内容更加清晰美观。
### 总结
以上是常见的 HTML 语句和标签，通过这些基本的标签，可以构建出简单的网页。HTML 与 CSS、JavaScript 结合使用可以制作更加复杂和交互性强的网页。