```
import requests
url = 'http://www.google.com'
html = requests.get(url)
html.encoding="utf-8"
if html.status_code == requests.codes.ok:
    print(html.text)
```
