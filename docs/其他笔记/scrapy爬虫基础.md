Scrapy 是一个用于提取网站数据的 Python 爬虫框架。它提供了构建、部署和管理网络爬虫的强大工具。以下是 Scrapy 的一些基础知识，帮助您开始构建爬虫项目。

## 1. 安装 Scrapy

使用以下命令安装 Scrapy：
```bash
pip install scrapy
```

## 2. 创建 Scrapy 项目

在项目目录中运行以下命令创建 Scrapy 项目：
```bash
scrapy startproject myproject
```

`myproject` 是项目名称，创建后会生成以下基本目录结构：

```
myproject/
├── myproject/
│   ├── __init__.py
│   ├── items.py
│   ├── middlewares.py
│   ├── pipelines.py
│   ├── settings.py
│   └── spiders/
└── scrapy.cfg
```

- `items.py`：定义数据结构（即要爬取的字段）。
- `pipelines.py`：定义数据存储、清理和处理。
- `settings.py`：定义爬虫设置，如延迟、用户代理等。
- `spiders/`：存放爬虫文件。

## 3. 创建 Spider（爬虫）

进入 `spiders/` 目录，创建一个爬虫文件，例如 `quotes_spider.py`。可以用以下命令创建一个新的爬虫：

```bash
scrapy genspider quotes quotes.toscrape.com
```

这会在 `spiders/` 目录下生成一个名为 `quotes.py` 的爬虫文件。此文件包含一个基础爬虫结构：

```python
import scrapy

class QuotesSpider(scrapy.Spider):
    name = "quotes"
    start_urls = [
        'http://quotes.toscrape.com/page/1/',
    ]

    def parse(self, response):
        for quote in response.css('div.quote'):
            yield {
                'text': quote.css('span.text::text').get(),
                'author': quote.css('small.author::text').get(),
                'tags': quote.css('div.tags a.tag::text').getall(),
            }

        next_page = response.css('li.next a::attr(href)').get()
        if next_page is not None:
            yield response.follow(next_page, self.parse)
```

- `name`：爬虫的名字，运行爬虫时用这个名字。
- `start_urls`：起始 URL 列表，爬虫会从这些页面开始。
- `parse()`：解析函数，用于处理页面的响应（`response`），提取数据。

在 `parse` 方法中，我们使用 `response.css` 选择器从页面中提取数据。

## 4. 运行爬虫

使用以下命令运行爬虫并将数据存储到 `quotes.json` 文件中：
```bash
scrapy crawl quotes -o quotes.json
```

## 5. Scrapy Shell

`Scrapy shell` 是一个交互式终端，帮助调试选择器和提取数据。可以使用以下命令进入 shell 进行测试：
```bash
scrapy shell 'http://quotes.toscrape.com/page/1/'
```

在 Scrapy shell 中，可以使用 `response.css` 或 `response.xpath` 来测试选择器并查看提取的数据。

## 6. Scrapy 项目中的关键文件

- **items.py**：定义数据结构。可以通过定义 `Item` 类来指定要爬取的字段：
  ```python
  import scrapy

  class QuoteItem(scrapy.Item):
      text = scrapy.Field()
      author = scrapy.Field()
      tags = scrapy.Field()
  ```

- **pipelines.py**：处理和存储数据。可以在这里定义数据清洗和保存逻辑。
  ```python
  class MyProjectPipeline:
      def process_item(self, item, spider):
          # 处理数据，例如清理或保存到数据库
          return item
  ```

- **settings.py**：Scrapy 的配置文件，用于设置爬虫的行为。
  - **ROBOTSTXT_OBEY**：遵循 robots.txt 文件。设为 `True` 遵循，`False` 不遵循。
  - **DOWNLOAD_DELAY**：设置爬虫的请求间隔，以防止过度请求。
  - **USER_AGENT**：定义用户代理。

## 7. 爬取多页面

在 `parse()` 方法中可以通过递归来爬取多页面数据。例如，上面代码中使用 `next_page` 跟踪 "下一页" 的链接。如果有下一页，则继续爬取。

## 8. 数据存储

运行爬虫时可以将数据存储为多种格式：

- JSON：`-o quotes.json`
- CSV：`-o quotes.csv`
- XML：`-o quotes.xml`

例如：
```bash
scrapy crawl quotes -o quotes.json
```

## 9. 常用选择器

- `response.css('selector')`：使用 CSS 选择器提取内容。
- `response.xpath('//selector')`：使用 XPath 选择器提取内容。

---

## 示例项目总结

1. 创建 Scrapy 项目并定义爬虫。
2. 在 `parse()` 方法中提取数据，使用 `yield` 返回数据。
3. 使用 Scrapy shell 调试选择器。
4. 运行爬虫并将数据保存到文件。

通过掌握这些基础步骤，您就可以构建一个简单的 Scrapy 爬虫项目。