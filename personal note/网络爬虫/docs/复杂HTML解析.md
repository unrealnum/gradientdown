# 复杂HTML解析



> 解析复杂的 HTML 页面，从中提取出所需的信息。



目标可能被淹没在一堆”没用“的格式文件中，并且可能具备难以<font color='cornflowerblue'>泛化</font>爬取的<font color='purple' size='5'>格式</font>

> 例如一个三行四列的表格，明天可能变成3行5列，使得其中数据变得不好摘取



## 泛化爬取方法



* “打印此页”
* 寻找隐藏在 JavaScript 文件里的信息
* 但是这个信息也许可以从网页的 URL 链接里获取
* 找找其他数据源
* 人工智能+机器识别泛化爬取（想吃牢饭或秃头就去做吧doge）



## 一般解析方法



* 爬取整个网络界面+异常处理+反爬虫规避
* 利用包装库内置引擎解析
* 通过函数读取相关元素形成数据集
* 数据集清洗
* 数据保存操作



## 常用函数



BeautifulSoup：`find()`和`find_all()`

