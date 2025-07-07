# Day 12

Done: Yes
Topic: Scope, Variables
Languages: Python
Difficulty: ⭐⭐
Date Started: April 19, 2023
Date Completed: April 19, 2023

## What I Learned Today

Learned....

################### Scope ####################

enemies = 1

def increase_enemies():

enemies = 2

print(f"enemies inside function: {enemies}")

increase_enemies()
print(f"enemies outside function: {enemies}")

OUTPUT →  2 & 1 enemies (different scopes)

def  function():

global variable (this is for explicitly transform the scope of a local variable)

variable+=1

Other and better way using return

variable = 1

def function():

return variable +1

variable = function()

## Key Concepts

- Namespaces: Where you create the variables are different (It also apply for anything you name, such as, functions created)
    - Local Scope:
        - You can only use it when is it inside th function
        - Exist whitin functions (inside the function)
    - Global Scope:
        - Is available anywhere in the code
        

Constants could be great for global scope. This ones should be UPPERCASE

### Quick Links

---

[**google.com**](http://www.google.com)

[**stackoverflow.com**](http://www.stackoverflow.com)

[**w3Schools.com**](https://www.w3schools.com/)

[**github.com**](https://github.com/)

## Code Snippets

```python

```

## Challenges Experienced

## Resources Used

add resources you used