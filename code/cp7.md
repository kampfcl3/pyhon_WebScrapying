# momoshop
```
import requests

URL = "https://www.momoshop.com.tw/search/"
URL_headers = {'user-agent': 'Mozilla/5.0 (window NT 10.0; Win64; x64)'
           'AppleWebKit/537.36(KHTML,like Gecko'
           'Chrome/63.0.3239.132 Safari/537.36'}

r = requests.get(URL+'searchShop.jsp?keyword=HTC',headers=URL_headers)


print(r.status_code)
if r.status_code == requests.codes.ok:
    r.encoding = "big5"
    print(r.text)

else:
    print("http請求錯誤..."+URL)
```
![image](https://github.com/kampfcl3/pyhon_WebScrapying/blob/main/pic/1q.png)


# wait 5 sec
```
import requests
import time

URL = "https://www.majortests.com/word-lists/word-list-01.html"
for i in range(1,10):
    url = URL.format(i)
    r = requests.get(url)
    print(r.status_code)
    print("等待5秒鐘...")
    time.sleep(5)
```
![image](https://github.com/kampfcl3/pyhon_WebScrapying/blob/main/pic/2q.png)

# ppt scrap
##remember pip install beautifulsoup4 and lxml
```
import requests
from bs4 import BeautifulSoup
URL = "https://www.ptt.cc/bbs/NBA/index.html"
DELETED = BeautifulSoup("<a href='deleted'>本文已刪除</a>","lxml").a

r = requests.get(URL)
if r.status_code == requests.codes.ok:
    r.encoding = "utf8"
    soup = BeautifulSoup(r.text,"lxml")
    tag_divs = soup.find_all("div",class_="r-ent")
    for tag in tag_divs:
        tag_a = tag.find("a") or DELETED
        print(tag_a["href"])
        print(tag_a.text)
        print(tag.find("div",class_="author").string)
else:
    print("HTTP 請求錯誤..."+URL)
```

![image](https://github.com/kampfcl3/pyhon_WebScrapying/blob/main/pic/3q.png)
# cookie
```
import requests
from bs4 import BeautifulSoup
URL = "https://www.ptt.cc/bbs/Gossiping/index.html"


r = requests.get(URL,cookies={"over18":"1"})
if r.status_code == requests.codes.ok:
    r.encoding = "utf8"
    soup = BeautifulSoup(r.text,"lxml")
    tag_divs = soup.find_all("div",class_="r-ent")
    for tag in tag_divs:
        if tag.find('a'):
            tag_a = tag.find("a")
            print(tag_a["href"])
            print(tag_a.text)
            print(tag.find("div", class_="author").string)
else:
    print("HTTP 請求錯誤..."+URL)

```

![image](https://github.com/kampfcl3/pyhon_WebScrapying/blob/main/pic/4q.png)

# 建立爬蟲目標的URL網址
```
from urllib.parse import urljoin

URL = "https://www.majortests.com/word-lists/word-list-01.html"
PTT = "https://www.ptt.cc/bbs/movie/index.html"

catalog = ["movie","NBA","Gossiping"]

for i in range(1,5):
    url = urljoin(URL,"world-list-0{0}.html".format(i))
    print(url)
for item in catalog:
    url = urljoin(PTT,"../{0}/index.html".format(item))
    print(url)
```

![image](https://github.com/kampfcl3/pyhon_WebScrapying/blob/main/pic/5q.png)

```

```
