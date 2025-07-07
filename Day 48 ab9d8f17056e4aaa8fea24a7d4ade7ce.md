# Day 48

Done: Yes
Topic: Selenium, webdriver
Languages: Python
Difficulty: ⭐⭐⭐
Date Started: July 4, 2023
Date Completed: July 7, 2023

## What I Learned Today

Learned....

## Key Concepts

- concept 1....

### Quick Links

---

[**google.com**](http://www.google.com)

[**stackoverflow.com**](http://www.stackoverflow.com)

[**w3Schools.com**](https://www.w3schools.com/)

[**github.com**](https://github.com/)

## Selenium

```python
from selenium import webdriver
page = "https://www.python.org/"
driver = webdriver.Chrome()

driver.get(page)
#price = driver.find_element(by="id", value="corePriceDisplay_desktop_feature_div")
#print(price.text)

#xpath_p = driver.find_element(by="xpath", value='//*[@id="corePriceDisplay_desktop_feature_div"]')
#print(xpath_p.text)

upcoming_events_date = driver.find_elements(by="xpath", value='//*[@id="content"]/div/section/div[2]/div[2]/div/ul/li/time')
upcoming_events_name = driver.find_elements(by="xpath", value='//*[@id="content"]/div/section/div[2]/div[2]/div/ul/li/a')

new_dict = {}
j = 0
for i in upcoming_events_date:
    lit_dict = {"time": i.text, "name": upcoming_events_name[j].text}
    new_dict[upcoming_events_date.index(i)] = lit_dict
    j+=1

print(new_dict)
```

## Autofill Challenge

```python
from selenium import webdriver
from selenium.webdriver.common.keys import Keys #import keys to tap
#page = "https://en.wikipedia.org/wiki/Main_Page"
# driver = webdriver.Chrome()
page = "http://secure-retreat-92358.herokuapp.com/"

options = webdriver.ChromeOptions()
options.add_experimental_option("detach", True) #dont close chrom
driver = webdriver.Chrome(options=options) #dont close chrom

driver.get(page)
# ---Wikipedia--
#price= driver.find_element(by="xpath", value='//*[@id="articlecount"]/a[1]')
#price.click()

#View_history = driver.find_element(by="link text", value="View history")
#View_history.click()

#search = driver.find_element(by="name", value="search")
#search.send_keys("Python")
#search.send_keys(Keys.ENTER)

#---Challenge---
name = "jose"
lastname = "perez"
email = "joseperez@gmail.com"
data = [name, lastname, email]

login = driver.find_elements(by="xpath", value='/html/body/form/input')
for i in range(len(login)):
    login[i].send_keys(data[i])

sign_up = driver.find_element(by="css selector", value="button")
sign_up.click()
```

## Cookie BOT

```python
from selenium import webdriver
import time

page ="https://orteil.dashnet.org/experiments/cookie/"
options = webdriver.ChromeOptions()
options.add_experimental_option("detach", True) #dont close chrom
driver = webdriver.Chrome(options=options)
driver.get(page)

cookie = driver.find_element(by="id", value="cookie")

timeout = time.time() + 60*5
segundos_5 = time.time() + 5
while True:
    cookie.click()
    if (time.time() > segundos_5):
        list_items = []
        items_store = driver.find_elements(by="css selector", value='#store div b')
        money = driver.find_element(by="id", value="money")
        for i in items_store[0:-1]:
            list_items.append(int((i.text.split("-")[1].strip()).replace(",", "")))

        for i in list_items[::-1]:
            if int(money.text) > i:
                index_list = list_items.index(i)
                break

        items_store[index_list].click()
        segundos_5 += 5
    if time.time() > timeout:
        cps = driver.find_element(by="id", value="cps")
        print(cps.text)
        break
```

## Challenges Experienced

## Resources Used

add resources you used