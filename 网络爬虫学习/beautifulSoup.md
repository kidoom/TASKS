**[Beautiful Soup](http://www.crummy.com/software/BeautifulSoup/) 是一个可以从HTML或XML文件中提取数据的Python库.它能够通过你喜欢的转换器实现惯用的文档导航,查找,修改文档的方式.**

使用bs能够解析HTML文件中的数据，同时他也是一个python库

```python
from bs4 import BeautifulSoup

file =open("./baidu01.html",'rb')
html = file.read()
bs = BeautifulSoup(html,'html.parser')
print(bs.title.string)
print(bs.a.string)
print(bs.head.string)
```

