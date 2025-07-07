# Day 26

Done: Yes
Topic: Comprehension, Dictionary, Lists, pandas
Difficulty: ⭐⭐⭐
Date Started: May 7, 2023
Date Completed: May 8, 2023

## What I Learned Today

Functions:

- .split(): get words from a sentence

Case 1:

numbers = [1, 2, 3]

new_list = []

for n in numbers:

add_1 = n+1

new_list.append(add_1)

Output > new_list = [2, 3, 4]

Same as:

numbers = [1, 2, 3]

new_list = [new_item for item in list]

new_list =[n+1 for n in numbers]

Output > new_list = [2, 3, 4]

With string:

name = “javier”

new_list = [letter for letter in name]

With range:

new_rlist = [n*2 for n in range(1,5)]

Output > [2, 4, 6, 8]

With conditional:

names = ["vale", "emilio", "cristob"]
new_names = [name for name in names if len(name)< 5]

Output > [”vale”]

Iterate through each row in pandas Dataframe:

data_frame.iterrows()

## Key Concepts

- List Comprehension: Works with list, strings, range, tuple, etcc
    
    expressión: new_list = [new_item for item in list]
    
- Conditional List Comprehension:
    
    expression: new_list = [new_item for item in list **if tes**t]
    
- Dictionary Comprehension:
    
    expression: new_dict = {new_key:new_value for item in list}
    
    Create value from a existing dictionary:
    
    expression : new_dict = {new_key:new_value for (key, value) in dict.items() if test}
    

### Quick Links

---

[**google.com**](http://www.google.com)

[**stackoverflow.com**](http://www.stackoverflow.com)

[**w3Schools.com**](https://www.w3schools.com/)

[**github.com**](https://github.com/)

## Check Same Values

```python
MAIN.PY 

with open("file1.txt") as data:
    number1 = data.readlines()

with open("file2.txt") as data:
    number2 = data.readlines()

new_list1 = [int(number1[number].replace("\n", "")) for number in range(0, len(number1))]
new_list2 = [int(number2[number].replace("\n", "")) for number in range(0, len(number2))]

result = [number for number in new_list1 if number in new_list2]

# Write your code above 👆

print(result)

FILE1.TXT

3
6
5
8
33
12
7
4
72
2
42
13

FILE2.TXT

3
6
13
5
7
89
12
3
33
34
1
344
42
```

## NATO Alphabet

```python
#TODO 1. Create a dictionary in this format:
#{"A": "Alfa", "B": "Bravo"}

data = pandas.read_csv("nato_phonetic_alphabet.csv")
letters = data["letter"].to_list()
words = data["code"].to_list()
code_dic = {letter: words[letters.index(letter)] for letter in letters}

#Other/Better way to do task 1:
phonetic_dict = {row.letter: row.code for (index, row) in data.iterrows()}

#TODO 2. Create a list of the phonetic code words from a word that the user inputs.

user_word = input("Enter word: ").upper()
user_letters = [user_letter for user_letter in user_word]
list_word = [code_dic[item] for item in user_letters]
print(list_word)

#Other/Better way to do task 2:
output_list = [phonetic_dict[letter] for letter in user_word]
print(output_list)

CSV

letter,code
A,Alfa
B,Bravo
C,Charlie
D,Delta
E,Echo
F,Foxtrot
G,Golf
H,Hotel
I,India
J,Juliet
K,Kilo
L,Lima
M,Mike
N,November
O,Oscar
P,Papa
Q,Quebec
R,Romeo
S,Sierra
T,Tango
U,Uniform
V,Victor
W,Whiskey
X,X-ray
Y,Yankee
Z,Zulu
```

## Some Examples

```python
student_dict = {
    "student": ["Angela", "James", "Lily"], 
    "score": [56, 76, 98]
}

#Looping through dictionaries:
for (key, value) in student_dict.items():
    #Access key and value
    pass

import pandas
student_data_frame = pandas.DataFrame(student_dict)

#Loop through rows of a data frame
for (index, row) in student_data_frame.iterrows():
    #Access index and row
    #Access row.student or row.score
    pass

# Keyword Method with iterrows()
# {new_key:new_value for (index, row) in df.iterrows()}
```

## Challenges Experienced

## Resources Used

add resources you used