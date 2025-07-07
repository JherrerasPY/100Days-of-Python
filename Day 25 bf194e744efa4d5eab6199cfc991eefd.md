# Day 25

Done: Yes
Topic: pandas
Languages: Python
Difficulty: ⭐⭐
Date Started: May 5, 2023
Date Completed: May 6, 2023

## What I Learned Today

```python
import pandas

data = pandas.read_csv("weather_data.csv")
print(data["temp"])
print(type(data)) # Data Frame
print(type(data["temp"])) #Series (like a list)

print(data.to_dict()) #Transform into dictionary

list_data_temp = data["temp"].to_list()
print(list_data_temp)

# Calculate de mean
j = 0
h = 0
for i in list_data_temp:
    j += i
    h += 1

print(j/h)

#mean with pandas
print(data["temp"].mean())

print(data["temp"].max())

#Get data in column
print(data["condition"])
print(data.condition)

#Get data in row
print(data[data.day == "Monday"])

print(data[data.temp == data.temp.max()]) #get max temp row

monday = data[data.day == "Monday"]
monday_temp = monday.temp

f_monday_temp = monday_temp*(9/5) + 32
print(f_monday_temp) # Farenheit

#Create a dataframe from scratch
data_dict = {
    "students" : ["Amy", "James", "Angela"],
    "scores" : [76, 56, 65]
}

datas = pandas.DataFrame(data_dict)
print(datas)
datas.to_csv("new_data")
```

[weather_data.csv](Day%2025%20bf194e744efa4d5eab6199cfc991eefd/weather_data.csv)

## Key Concepts

- concept 1....

### Quick Links

---

[**google.com**](http://www.google.com)

[**stackoverflow.com**](http://www.stackoverflow.com)

[**w3Schools.com**](https://www.w3schools.com/)

[**github.com**](https://github.com/)

## U.S.A States Game

```python
import turtle
import pandas
from write_state import WriteStates

screen = turtle.Screen()
screen.title("U.S States Game")
image = "blank_states_img.gif"
screen.addshape(image)
turtle.shape(image)

data = pandas.read_csv("50_states.csv")

score = 0
game_on = True
correct_guess = []
while game_on:
    answer_state = screen.textinput(f"Guest State ({score}/ 50)", "What's another state name?").title()
    if answer_state in data.state.to_list():
        var = data[data.state == answer_state]
        x = int(var.x)
        y = int(var.y)
        write_state = WriteStates(answer_state, (x, y))
        correct_guess.append(answer_state)
        score += 1
    else:
        print(correct_guess)
        game_on = False
        states_list = data.state.to_list()
        for i in correct_guess:
            states_list.remove(i)
        df = pandas.DataFrame(states_list)
        df.to_csv("missing_states.csv") 

WRITING_STATE.PY

from turtle import Turtle

FONT = ("Courier", 8, "normal")

class WriteStates(Turtle):

    def __init__(self, state, position):
        super().__init__()
        self.hideturtle()
        self.penup()
        self.goto(position)
        self.write(f"{state}", True, "center", FONT)
```

## Challenges Experienced

## Resources Used

add resources you used