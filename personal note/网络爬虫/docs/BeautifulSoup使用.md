# BeautifulSoup使用



[toc]

> BeautifulSoup 尝试化平淡为神奇。它通过定位 HTML 标签来 格式化和组织复杂的网页信息，用简单易用的 Python 对象为我们展现 XML 结构信息。





```python
from urllib.request import urlopen
from bs4 import BeautifulSoup

html =urlopen('http://www.pythonscraping.com/pages/page1.html')
bs=BeautifulSoup(html,'html.parser')
print(bs.h1)
```



当你创建一个 BeautifulSoup 对象时，需要传入两个参数:

```
bs=BeautifulSoup(html,'html.parser')
```

* 第一个参数是该对象所基于的 HTML 文本
* 第二个参数指定了你希望 BeautifulSoup 用来 创建该对象的解析器



## 常用解析器

>  html.parser 是 Python 3 中的一个解析器



1. 另一个常用的解析器是 lxml（anaconda中有）

>  和 html.parser 相比，lxml 的优点在于解析“杂乱”或者包含错误语法的 HTML 代码的性 能更优一些。它可以容忍并修正一些问题，例如未闭合的标签、未正确嵌套的标签，以及 缺失的头（head）标签或正文（body）标签。lxml 也比 html.parser 更快



在网页抓取中速度并不是一个必备的优势，<font color='red' size='5'>甚至可能是劣势</font>



2. 另外一个常用的 HTML 解析器是 html5lib。和 lxml 一样，html5lib 也是一个具有容错性 的解析器，它甚至可以容忍语法更糟糕的 HTML。它也依赖于外部依赖，并且比 lxml 和 html.parser 都慢。



## 异常处理

> Web 是十分复杂的。网页数据格式不友好、网站服务器死机、目标数据的标签找不到，都 是很麻烦的事情。网页抓取最痛苦的遭遇之一，就是爬虫运行的时候你洗洗睡了，梦想着 明天一早数据就都会抓取好放在数据库里, 结果第二天醒来，你看到的却是一个因某种数据格式异常导致运行错误的爬虫，在前一天当你不再盯着屏幕去睡觉之后，没过一会儿 爬虫就不再运行了。那个时候，你可能想骂发明网站（以及那些奇葩的网络数据格式）的 人，但是你真正应该斥责的人是你自己，为什么一开始不估计可能会出现的<font color='red' size ='6'>异常!</font>



#### 从urlopen说起......

* 404/500NoFound异常
  * （404）网页不存在
  * （500）服务器不存在

利用try...except句式捕获错误/执行另一个方案

```python
try:
 html = urlopen('http://www.pythonscraping.com/pages/page1.html')
except HTTPError as e:
 print(e)
except URLError as e:
 print('The server could not be found!')
```

> 如果你想要调用的标签不存在，BeautifulSoup 就会返 回 None 对象。不过，如果再调用这个 None 对象下面的子标签，就会发生 <font color='red' size='5'>AttributeError 错误</font>

那么怎么才能避免这两种情形的异常呢？最简单的方式就是对两种情形进行检查：

```python
try:
 badContent = bs.nonExistingTag.anotherTag
except AttributeError as e:
 print('Tag was not found')
else:
 if badContent == None:
 print ('Tag was not found')
 else:
 print(badContent)
```



<font color='purple' size='6'>创造一个函数专门用于异常处理</font>



> 在写爬虫的时候，思考代码的总体格局，让代码既可以捕捉异常又容易阅读，这是很重要 的。如果你还希望重用大量代码，那么拥有像 getSiteHTML 和 getTitle 这样的通用函数 （具有周密的异常处理功能）会让快速、稳定地抓取网页变得简单易行



