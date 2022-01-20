## 通过urllib库可以进行浏览器的访问，获取网页信息

```python
import  urllib.request
#get请求
# response = urllib.request.urlopen("http://212.129.245.115/geek#/")
# print(response.read().decode("utf-8"))

#获取post请求

# import urllib.parse
# data = bytes(urllib.parse.urlencode({"hello":"world"}),encoding ="utf-8")
# response = urllib.request.urlopen("http://httpbin.org/post",data =data)
# print(response.read().decode("utf-8"))

# response = urllib.request.urlopen("http://httpbin.org/get")
# print(response.read().decode("utf-8"))
response = urllib.request.urlopen("http://httpbin.org/get")
print(response.status)

```

## 重新封装请求对象

```python
url = "http://httpbin.org/post"
headers ={
"User-Agent":" Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36 Edg/97.0.1072.55"
}#模拟浏览器发送用户请求
data =bytes(urllib.parse.urlencode({'ok':"2"}),encoding ="utf-8")
req = urllib.request.Request(url=url,data=data,headers=headers,method="POST")
response = urllib.request.urlopen(req)
print(response.read().decode("utf-8"))
```

