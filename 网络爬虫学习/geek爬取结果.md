<<<<<<< Updated upstream
# GEEK爬虫思路

## 起初思路：刚开始时想通过requests请求获得网页源码，然后用正则表达式解析 通过excel完成整个项目，但是当我用request请求时发现获得的源码是不完整的 ，在我困惑了好几天后，我换了一种思路

## 1.遇到的问题

开发者模式和网页的源代码不一致

在我查阅资料（csdn，知乎，google）后我是这样认为的

网页源代码：服务器原封不动发送给客户端的代码

开发者模式：客户端运行了js脚本后，生成的网页源文件

在我打开f12获得网络请求时  观察到geek网页通过webpackjsonp打包js 实现异步加载

因此我想是否有一种方法能够获取动态网页源代码，而不是获取静态的网页源码

所以我学习了selenium 来模拟浏览器访问网页的过程，进一步实现网页的爬取

代码如下

```python
import requests
from selenium import webdriver
import selenium
import xlwt #进行excel
from selenium.webdriver.common.by import By #防止警告
import  xlwt
import os
if not os.path.exists('./img'):
    os.mkdir('./img')


def saveimg(url):
    pages = requests.get(url)
    r = pages.content
    with open('./img/b.png', 'wb') as f:
        f.write(r)





driver=webdriver.Chrome()
driver.get('http://212.129.245.115/geek#/')
datalist = []
data = []
node01 = driver.find_element(By.XPATH,'//*[@id="wen1"]')
data.append(node01.text)
node02 = driver.find_element(By.XPATH,'//*[@id="wen2"]')
data.append(node02.text)
node03 = driver.find_element(By.XPATH,'/html/body/div/div[4]/div[2]/div')
data.append(node03.text)
node04 = driver.find_element(By.XPATH,'//*[@id="wen3"]')
data.append(node04.text)
node05 = driver.find_element(By.XPATH,'//*[@id="bs"]')
data.append(node05.text)
node06 = driver.find_element(By.XPATH,'//*[@id="wen4"]')
data.append(node06.text)
datalist.append(data)
node07 = driver.find_element(By.XPATH,'//*[@id="allquestion"]')
data.append(node07)
datalist.append(data)
filename = 'geekwords.txt'
with open(filename,'w',encoding='utf-8')as file_object:
    file_object.writelines(str(datalist))

img_url = driver.find_element(By.XPATH,'/html/body/div/div[1]/button[1]/img').get_attribute('src')
img_url1 =driver.find_element(By.XPATH,'//*[@id="gd"]').get_attribute('src')
pages = requests.get(img_url1)
a = pages.content
with open('./img/b.png', 'wb') as f:
    f.write(a)
page = requests.get(img_url)
img1 = page.content
with open('./img/a.png','wb')as f:
    f.write(img1)

img_url2 = driver.find_element(By.XPATH,'//*[@id="monkey"]').get_attribute('src')
pages1 = requests.get(img_url2)
c = pages1.content
with open('./img/c.png', 'wb') as f:
    f.write(c)

img_url3 = driver.find_element(By.XPATH,'//*[@id="houzi"]').get_attribute('src')
pages2 = requests.get(img_url3)
d = pages2.content
with open('./img/d.png', 'wb') as f:
    f.write(d)

img_url4 = driver.find_element(By.XPATH,'//*[@id="houzi"]').get_attribute('src')
pages3 = requests.get(img_url4)
e = pages3.content
with open('./img/e.png', 'wb') as f:
    f.write(e)

img_url5 = driver.find_element(By.XPATH,'//*[@id="xiangjiao"]').get_attribute('src')
pages4 = requests.get(img_url5)
f1 = pages4.content
with open('./img/f.png', 'wb') as f:
    f.write(f1)

img_url6 = driver.find_element(By.XPATH,'//*[@id="chanpin"]').get_attribute('src')
pages5 = requests.get(img_url6)
g = pages5.content
with open('./img/g.png', 'wb') as f:
    f.write(g)

img_url7 = driver.find_element(By.XPATH,'//*[@id="chanpin2"]').get_attribute('src')
pages6 = requests.get(img_url7)
h = pages6.content
with open('./img/h.png', 'wb') as f:
    f.write(h)

img_url8 = driver.find_element(By.XPATH,'//*[@id="heiban"]').get_attribute('src')
pages7 = requests.get(img_url8)
i = pages7.content
with open('./img/i.png', 'wb') as f:
    f.write(i)

img_url9 = driver.find_element(By.XPATH,'//*[@id="prx"]').get_attribute('src')
pages8 = requests.get(img_url9)
j = pages8.content
with open('./img/j.png', 'wb') as f:
    f.write(j)

img_url10 = driver.find_element(By.XPATH,'//*[@id="ai"]').get_attribute('src')
pages9 = requests.get(img_url10)
k = pages9.content
with open('./img/k.png', 'wb') as f:
    f.write(k)


img_url11 = driver.find_element(By.XPATH,'//*[@id="ai2"]').get_attribute('src')
pages10 = requests.get(img_url11)
l = pages10.content
with open('./img/l.png', 'wb') as f:
    f.write(l)

img_url12 = driver.find_element(By.XPATH,'//*[@id="ai3"]').get_attribute('src')
pages11 = requests.get(img_url12)
m = pages11.content
with open('./img/m.png', 'wb') as f:
    f.write(m)

img_url13 = driver.find_element(By.XPATH,'//*[@id="aix"]').get_attribute('src')
pages12 = requests.get(img_url13)
n = pages12.content
with open('./img/n.png', 'wb') as f:
    f.write(n)

img_url14 = driver.find_element(By.XPATH,'//*[@id="lion"]').get_attribute('src')
pages13 = requests.get(img_url14)
o = pages13.content
with open('./img/o.png', 'wb') as f:
    f.write(o)

img_url15 = driver.find_element(By.XPATH,'//*[@id="shizi2"]').get_attribute('src')
pages14 = requests.get(img_url15)
s = pages14.content
with open('./img/s.png', 'wb') as f:
    f.write(s)

img_url16 = driver.find_element(By.XPATH,'//*[@id="chap"]').get_attribute('src')
pages15 = requests.get(img_url16)
t = pages15.content
with open('./img/t.png', 'wb') as f:
    f.write(t)

img_url17 = driver.find_element(By.XPATH,'//*[@id="beijp"]').get_attribute('src')
pages16 = requests.get(img_url17)
u = pages16.content
with open('./img/u.png', 'wb') as f:
    f.write(u)

img_url18 = driver.find_element(By.XPATH,'//*[@id="time"]').get_attribute('src')
pages17 = requests.get(img_url18)
v = pages17.content
with open('./img/v.png', 'wb') as f:
    f.write(v)

img_url19 = driver.find_element(By.XPATH, '//*[@id="speech"]').get_attribute('src')
pages20 = requests.get(img_url19)
w = pages20.content
with open('./img/w.png', 'wb') as f:
    f.write(w)

img_url20 = driver.find_element(By.XPATH, '//*[@id="douyan"]').get_attribute('src')
pages21 = requests.get(img_url20)
x = pages21.content
with open('./img/x.png', 'wb') as f:
    f.write(x)



img_url21 = driver.find_element(By.XPATH, '//*[@id="douyan"]').get_attribute('src')
pages22 = requests.get(img_url21)
x = pages22.content
with open('./img/x.png', 'wb') as f:
    f.write(x)

img_url22 = driver.find_elements(By.XPATH, '//*[@id="lefts"]').get_attribute('src')
pages23 = requests.get(img_url22)
y = pages23.content
with open('./img/y.png', 'wb') as f:
    f.write(y)

img_url23 = driver.find_elements(By.XPATH, '//*[@id="rights"]').get_attribute('src')
pages24 = requests.get(img_url23)
z = pages24.content
with open('./img/z.png', 'wb') as f:
    f.write(z)
```

思路：**完成基本配置后，我通过xpath解析节点获取网页文字和信息**，**但是我的代码在处理图片方面显得过于冗余了，可以进一步优化，以为我暂时还没有学会xpath的遍历（也可能是我前端没有学好） 所以目前我是一个个写的 比较笨的方法，所以希望过段时间我能优化一下自己的代码。**

成果展示:

网页文字：![img](https://github.com/kidoom/TASKS/blob/master/%E7%BD%91%E7%BB%9C%E7%88%AC%E8%99%AB%E5%AD%A6%E4%B9%A0/geekwords.png)
图片爬取：![img](https://github.com/kidoom/TASKS/blob/master/%E7%BD%91%E7%BB%9C%E7%88%AC%E8%99%AB%E5%AD%A6%E4%B9%A0/2022-01-20_205513.png)
=======
# GEEK爬虫思路

## 起初思路：刚开始时想通过requests请求获得网页源码，然后用正则表达式解析 通过excel完成整个项目，但是当我用request请求时发现获得的源码是不完整的 ，在我困惑了好几天后，我换了一种思路

## 1.遇到的问题

开发者模式和网页的源代码不一致

在我查阅资料（csdn，知乎，google）后我是这样认为的

网页源代码：服务器原封不动发送给客户端的代码

开发者模式：客户端运行了js脚本后，生成的网页源文件

在我打开f12获得网络请求时  观察到geek网页通过webpackjsonp打包js 实现异步加载

因此我想是否有一种方法能够获取动态网页源代码，而不是获取静态的网页源码

所以我学习了selenium 来模拟浏览器访问网页的过程，进一步实现网页的爬取

代码如下

```python
import requests
from selenium import webdriver
import selenium
import xlwt #进行excel
from selenium.webdriver.common.by import By #防止警告
import  xlwt
import os
if not os.path.exists('./img'):
    os.mkdir('./img')


def saveimg(url):
    pages = requests.get(url)
    r = pages.content
    with open('./img/b.png', 'wb') as f:
        f.write(r)





driver=webdriver.Chrome()
driver.get('http://212.129.245.115/geek#/')
datalist = []
data = []
node01 = driver.find_element(By.XPATH,'//*[@id="wen1"]')
data.append(node01.text)
node02 = driver.find_element(By.XPATH,'//*[@id="wen2"]')
data.append(node02.text)
node03 = driver.find_element(By.XPATH,'/html/body/div/div[4]/div[2]/div')
data.append(node03.text)
node04 = driver.find_element(By.XPATH,'//*[@id="wen3"]')
data.append(node04.text)
node05 = driver.find_element(By.XPATH,'//*[@id="bs"]')
data.append(node05.text)
node06 = driver.find_element(By.XPATH,'//*[@id="wen4"]')
data.append(node06.text)
datalist.append(data)
node07 = driver.find_element(By.XPATH,'//*[@id="allquestion"]')
data.append(node07)
datalist.append(data)
filename = 'geekwords.txt'
with open(filename,'w',encoding='utf-8')as file_object:
    file_object.writelines(str(datalist))

img_url = driver.find_element(By.XPATH,'/html/body/div/div[1]/button[1]/img').get_attribute('src')
img_url1 =driver.find_element(By.XPATH,'//*[@id="gd"]').get_attribute('src')
pages = requests.get(img_url1)
a = pages.content
with open('./img/b.png', 'wb') as f:
    f.write(a)
page = requests.get(img_url)
img1 = page.content
with open('./img/a.png','wb')as f:
    f.write(img1)

img_url2 = driver.find_element(By.XPATH,'//*[@id="monkey"]').get_attribute('src')
pages1 = requests.get(img_url2)
c = pages1.content
with open('./img/c.png', 'wb') as f:
    f.write(c)

img_url3 = driver.find_element(By.XPATH,'//*[@id="houzi"]').get_attribute('src')
pages2 = requests.get(img_url3)
d = pages2.content
with open('./img/d.png', 'wb') as f:
    f.write(d)

img_url4 = driver.find_element(By.XPATH,'//*[@id="houzi"]').get_attribute('src')
pages3 = requests.get(img_url4)
e = pages3.content
with open('./img/e.png', 'wb') as f:
    f.write(e)

img_url5 = driver.find_element(By.XPATH,'//*[@id="xiangjiao"]').get_attribute('src')
pages4 = requests.get(img_url5)
f1 = pages4.content
with open('./img/f.png', 'wb') as f:
    f.write(f1)

img_url6 = driver.find_element(By.XPATH,'//*[@id="chanpin"]').get_attribute('src')
pages5 = requests.get(img_url6)
g = pages5.content
with open('./img/g.png', 'wb') as f:
    f.write(g)

img_url7 = driver.find_element(By.XPATH,'//*[@id="chanpin2"]').get_attribute('src')
pages6 = requests.get(img_url7)
h = pages6.content
with open('./img/h.png', 'wb') as f:
    f.write(h)

img_url8 = driver.find_element(By.XPATH,'//*[@id="heiban"]').get_attribute('src')
pages7 = requests.get(img_url8)
i = pages7.content
with open('./img/i.png', 'wb') as f:
    f.write(i)

img_url9 = driver.find_element(By.XPATH,'//*[@id="prx"]').get_attribute('src')
pages8 = requests.get(img_url9)
j = pages8.content
with open('./img/j.png', 'wb') as f:
    f.write(j)

img_url10 = driver.find_element(By.XPATH,'//*[@id="ai"]').get_attribute('src')
pages9 = requests.get(img_url10)
k = pages9.content
with open('./img/k.png', 'wb') as f:
    f.write(k)


img_url11 = driver.find_element(By.XPATH,'//*[@id="ai2"]').get_attribute('src')
pages10 = requests.get(img_url11)
l = pages10.content
with open('./img/l.png', 'wb') as f:
    f.write(l)

img_url12 = driver.find_element(By.XPATH,'//*[@id="ai3"]').get_attribute('src')
pages11 = requests.get(img_url12)
m = pages11.content
with open('./img/m.png', 'wb') as f:
    f.write(m)

img_url13 = driver.find_element(By.XPATH,'//*[@id="aix"]').get_attribute('src')
pages12 = requests.get(img_url13)
n = pages12.content
with open('./img/n.png', 'wb') as f:
    f.write(n)

img_url14 = driver.find_element(By.XPATH,'//*[@id="lion"]').get_attribute('src')
pages13 = requests.get(img_url14)
o = pages13.content
with open('./img/o.png', 'wb') as f:
    f.write(o)

img_url15 = driver.find_element(By.XPATH,'//*[@id="shizi2"]').get_attribute('src')
pages14 = requests.get(img_url15)
s = pages14.content
with open('./img/s.png', 'wb') as f:
    f.write(s)

img_url16 = driver.find_element(By.XPATH,'//*[@id="chap"]').get_attribute('src')
pages15 = requests.get(img_url16)
t = pages15.content
with open('./img/t.png', 'wb') as f:
    f.write(t)

img_url17 = driver.find_element(By.XPATH,'//*[@id="beijp"]').get_attribute('src')
pages16 = requests.get(img_url17)
u = pages16.content
with open('./img/u.png', 'wb') as f:
    f.write(u)

img_url18 = driver.find_element(By.XPATH,'//*[@id="time"]').get_attribute('src')
pages17 = requests.get(img_url18)
v = pages17.content
with open('./img/v.png', 'wb') as f:
    f.write(v)

img_url19 = driver.find_element(By.XPATH, '//*[@id="speech"]').get_attribute('src')
pages20 = requests.get(img_url19)
w = pages20.content
with open('./img/w.png', 'wb') as f:
    f.write(w)

img_url20 = driver.find_element(By.XPATH, '//*[@id="douyan"]').get_attribute('src')
pages21 = requests.get(img_url20)
x = pages21.content
with open('./img/x.png', 'wb') as f:
    f.write(x)



img_url21 = driver.find_element(By.XPATH, '//*[@id="douyan"]').get_attribute('src')
pages22 = requests.get(img_url21)
x = pages22.content
with open('./img/x.png', 'wb') as f:
    f.write(x)

img_url22 = driver.find_elements(By.XPATH, '//*[@id="lefts"]').get_attribute('src')
pages23 = requests.get(img_url22)
y = pages23.content
with open('./img/y.png', 'wb') as f:
    f.write(y)

img_url23 = driver.find_elements(By.XPATH, '//*[@id="rights"]').get_attribute('src')
pages24 = requests.get(img_url23)
z = pages24.content
with open('./img/z.png', 'wb') as f:
    f.write(z)
```

思路：**完成基本配置后，我通过xpath解析节点获取网页文字和信息**，**但是我的代码在处理图片方面显得过于冗余了，可以进一步优化，以为我暂时还没有学会xpath的遍历（也可能是我前端没有学好） 所以目前我是一个个写的 比较笨的方法，所以希望过段时间我能优化一下自己的代码。**

成果展示：

网页文字：![img](https://github.com/kidoom/TASKS/blob/master/%E7%BD%91%E7%BB%9C%E7%88%AC%E8%99%AB%E5%AD%A6%E4%B9%A0/geekwords.png)
图片爬取：![img](https://github.com/kidoom/TASKS/blob/master/%E7%BD%91%E7%BB%9C%E7%88%AC%E8%99%AB%E5%AD%A6%E4%B9%A0/2022-01-20_205513.png)
>>>>>>> Stashed changes
