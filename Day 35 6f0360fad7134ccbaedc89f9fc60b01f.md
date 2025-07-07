# Day 35

Done: Yes
Topic: API, Authentication
Languages: Python
Difficulty: ⭐⭐⭐
Date Started: June 19, 2023
Date Completed: June 21, 2023

## What I Learned Today

Twilio to send SMS

## Key Concepts

- API Key: limit access authentication
- Environment variables: Se pueden modificar sin tocar el código (Benefic: Seguridad y comodidad) [Donde almacenamos ej: API_Key]
    - Crear Variable Env:
        
        export AUTH_TOKEN={token}
        

### Quick Links

---

[**google.com**](http://www.google.com)

[**stackoverflow.com**](http://www.stackoverflow.com)

[**w3Schools.com**](https://www.w3schools.com/)

[**github.com**](https://github.com/)

## Send SMS Rainning

```python
import requests
from twilio.rest import Client

account_sid = "xxxx"
auth_token = "xxxx"

parameters = {
    "lat": -33.86,
    "lon": 151.20,
    "exclude": "current,minutely,daily",
    "appid": "xxxx",
}

response = requests.get(url="https://api.openweathermap.org/data/2.5/forecast", params=parameters)
response.raise_for_status()
data = response.json()

codes_12 = []
Rain = False
for i in range(0, 12):
    condition = data["list"][i]["weather"][0]["id"]
    codes_12.append(condition)
    if int(condition) < 700:
        Rain = True

if Rain:
    client = Client(account_sid,auth_token)
    message = client.messages \
        .create(
        body="Bring umbrela",
        from_='+000000000',
        to='+000000000'
    )

    print(message.status)
```

## Challenges Experienced

## Resources Used

add resources you used