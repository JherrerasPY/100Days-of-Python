# Day 23

Done: Yes
Topic: Game, Turtle
Languages: Python
Difficulty: ⭐⭐⭐
Date Started: April 29, 2023
Date Completed: May 1, 2023

## What I Learned Today

Game: Turtle Crossing

## Key Concepts

- concept 1....

### Quick Links

---

[**google.com**](http://www.google.com)

[**stackoverflow.com**](http://www.stackoverflow.com)

[**w3Schools.com**](https://www.w3schools.com/)

[**github.com**](https://github.com/)

## Code Snippets

```python
MAIN.PY

import time
from turtle import Screen
from player import Player
from car_manager import CarManager
from scoreboard import Scoreboard

scoreboard = Scoreboard(-220, 250)

screen = Screen()
screen.setup(width=600, height=600)
screen.tracer(0)

player = Player()
screen.listen()
screen.onkey(player.move, "Up")

car_list = []

def generate_car():
    new_car = CarManager()
    car_list.append(new_car)

game_is_on = True
generate_car()

for i in range(0, 40):
    generate_car()

while game_is_on:
    time.sleep(scoreboard.times)
    screen.update()
    for i in range(0, len(car_list)):
        car_list[i].car_move()
        if car_list[i].xcor() < -330:
            car_list.remove(car_list[i])
            generate_car()
        if player.distance(car_list[i]) < 20:
            scoreboard.game_over()
            game_is_on = False
    if player.ycor() == 280:
        player.goto(0, -280)
        scoreboard.update_level()
        scoreboard.velocity()

screen.exitonclick()

PLAYER.PY

from turtle import Turtle

STARTING_POSITION = (0, -280)
MOVE_DISTANCE = 10
FINISH_LINE_Y = 280

class Player(Turtle):
    def __init__(self,):
        super().__init__(shape="turtle")
        self.penup()
        self.goto(STARTING_POSITION)
        self.setheading(90)

    def move(self):
        self.forward(MOVE_DISTANCE)

    def original_position(self):
        pass

CAR_MANAGER.PY

from turtle import Turtle
import random as r

COLORS = ["red", "orange", "yellow", "green", "blue", "purple"]
STARTING_MOVE_DISTANCE = 5
MOVE_INCREMENT = 10

class CarManager(Turtle):
    def __init__(self):
        super().__init__(shape="square")
        self.penup()
        self.rand_y = r.randint(-250, 250)
        self.rand_x = r.randint(300, 1500)
        self.rand_color = r.choice(COLORS)
        self.color(self.rand_color)
        self.goto(self.rand_x, self.rand_y)
        self.shapesize(1, 2)
        self.setheading(180)

    def car_move(self):
        self.forward(STARTING_MOVE_DISTANCE)

SCOREBOARD.PY

from turtle import Turtle

FONT = ("Courier", 24, "normal")

class Scoreboard(Turtle):

    def __init__(self, XX, YY):
        super().__init__()
        self.times = 0.1
        self.level = 0
        self.hideturtle()
        self.penup()
        self.x = XX
        self.y = YY
        self.goto(XX, YY)
        self.update_level()

    def game_over(self):
        self.goto(0, 0)
        self.write(f"GAME OVER.", True, "center", FONT)

    def update_level(self):
        self.clear()
        self.goto(self.x, self.y)
        self.level += 1
        self.write(f"Level: {self.level}", True, "center", FONT)

    def velocity(self):
        self.times *= 0.5
```

## Challenges Experienced

[Solution+-+turtle-crossing-final.zip](Day%2023%20b8012053ccab4ebd8957aa7df8a1f9ac/Solution-turtle-crossing-final.zip)

## Resources Used

add resources you used