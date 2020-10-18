![image](https://github.com/kampfcl3/pyhon_WebScrapying/blob/main/pic/1.png)
#momoshop
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


#wait 5 sec
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
![image](https://github.com/kampfcl3/pyhon_WebScrapying/upload/main/pic)
