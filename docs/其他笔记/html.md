## HTML相关

HTML（超文本标记语言）是一种用于创建网页的标记语言。HTML 使用标签（tag）来定义页面内容的结构，比如标题、段落、列表、图片、链接等。以下是一些常用的 HTML 标签和语句。

### 1. HTML 基本结构
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

### 2. 标题标签
使用 `<h1>` 到 `<h6>` 标签来定义标题，`<h1>` 是最大的标题，`<h6>` 是最小的标题。

```html
<h1>这是一级标题</h1>
<h2>这是二级标题</h2>
<h3>这是三级标题</h3>
```

### 3. 段落标签
使用 `<p>` 标签定义段落。

```html
<p>这是一个段落。</p>
<p>这是另一个段落。</p>
```

### 4. 链接
使用 `<a>` 标签创建超链接，`href` 属性指定链接目标。

```html
<a href="https://www.example.com">访问 Example 网站</a>
```

### 5. 图片
使用 `<img>` 标签插入图片，`src` 属性指定图片 URL，`alt` 属性用于描述图片。

```html
<img src="image.jpg" alt="图片描述">
```

### 6. 列表
#### 无序列表
使用 `<ul>` 和 `<li>` 标签创建无序列表。

```html
<ul>
  <li>项目 1</li>
  <li>项目 2</li>
  <li>项目 3</li>
</ul>
```

#### 有序列表
使用 `<ol>` 和 `<li>` 标签创建有序列表。

```html
<ol>
  <li>第一步</li>
  <li>第二步</li>
  <li>第三步</li>
</ol>
```

### 7. 表格
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

### 8. 表单
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

### 9. 分割线
使用 `<hr>` 标签创建水平分割线。

```html
<p>这是第一段。</p>
<hr>
<p>这是第二段。</p>
```

### 10. 注释
使用 `<!-- ... -->` 来添加注释，注释内容不会显示在网页上。

```html
<!-- 这是一个注释 -->
<p>这是一个段落。</p>
```

### 11. 强调和斜体
使用 `<strong>` 或 `<b>` 标签使文本加粗，使用 `<em>` 或 `<i>` 标签使文本斜体。

```html
<p>这是 <strong>加粗</strong> 的文字。</p>
<p>这是 <em>斜体</em> 的文字。</p>
```

### 12. 内联样式
使用 `style` 属性为标签添加内联样式。

```html
<p style="color: blue; font-size: 20px;">这是蓝色的文字。</p>
```

### 13. 内部和外部样式
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

### 14. JavaScript 脚本
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

### 总结
以上是常见的 HTML 语句和标签，通过这些基本的标签，可以构建出简单的网页。HTML 与 CSS、JavaScript 结合使用可以制作更加复杂和交互性强的网页。