# Простой парсер на Python: разбор для новичков

Покажу, как сделать базовый парсер, разберу каждую строчку и типичные ошибки.

## Что понадобится

- Python 3.8+
- `requests`
- `beautifulsoup4`

Установить можно командой:

```bash
pip install requests beautifulsoup4
import requests

url = "https://example.com"
response = requests.get(url)
print(response.status_code)
from bs4 import BeautifulSoup

html = response.text
soup = BeautifulSoup(html, "html.parser")
titles = soup.find_all("h1")
for t in titles:
    print(t.text)
