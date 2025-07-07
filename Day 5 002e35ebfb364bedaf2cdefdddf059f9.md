# Day 5

Done: Yes
Topic: Loops
Languages: Python
Difficulty: ⭐⭐
Date Started: March 19, 2023
Date Completed: March 23, 2023

## What I Learned Today

Functions:

max()

min()

shuffle() → reorder list

For Loop:
→ for values in list:
       print(values) → output: all values in the list

Loop with rangeFor i in range(0,n,step):

Print i

Range:
→ for values in range(1,10) *10 not included

print(values) → output: 1,2,3,4,5,6,7,8,9

eg:

even numbers:

for even_number in range(2,101,2)

print(even_number)

## Key Concepts

- concept 1....

### Quick Links

---

[**google.com**](http://www.google.com)

[**stackoverflow.com**](http://www.stackoverflow.com)

[**w3Schools.com**](https://www.w3schools.com/)

[**github.com**](https://github.com/)

## Highest Score (Without Max)

```python
x = 0
for score in student_scores:
    if score > x:
        x = score
print(f"The highest score in the class is: {x}")
```

## FizzBuzz Game

```python
for number in range(1,101):
    if number %3==0 and number%5 ==0:
        print("FizzBuzz")
    elif number %3==0:
        print("Fizz")
    elif number%5==0:
        print("Buzz")
    else:
        print(number)
```

## Challenges Experienced

## Resources Used

add resources you used