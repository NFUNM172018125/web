### web学习

```
from requests_html import HTMLSession

session = HTMLSession()

r = session.get("https://news.cnblogs.com/n/recommend")

# 通过CSS找到新闻标签
news = r.html.find('h2.news_entry > a')

for new in news:
    print("新闻标题",new.text)  # 获得新闻标题
    print("新闻链接",new.absolute_links)  # 获得新闻链接
 ```
 
 ```
 from requests_html import HTMLSession

session = HTMLSession()

r = session.get("https://www.liepin.com/zhaopin/?key=web+mining")

# 通过xpath找到工作标签
news = r.html.xpath('//div[@class="job-info"]/h3/a')

for new in news:
    print(new.text)  # 获得工作标题
    print(new.absolute_links)  # 获得工作链接
```

**//** 取以下所有层

* [@按照属性]取条件
