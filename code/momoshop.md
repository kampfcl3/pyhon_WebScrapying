![image](https://github.com/kampfcl3/pyhon_WebScrapying/blob/main/pic/1.png)
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
