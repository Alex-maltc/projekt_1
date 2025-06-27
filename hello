"""
projekt_1.py: první projekt do Engeto Online Python Akademie
author: Aleksei Maltcev
email: alexmal@post.cz
"""
import re

TEXTS = {
    "text1": '''Situated about 10 miles west of Kemmerer,
    Fossil Butte is a ruggedly impressive
    topographic feature that rises sharply
    some 1000 feet above Twin Creek Valley
    to an elevation of more than 7500 feet
    above sea level. The butte is located just
    north of US 30 and the Union Pacific Railroad,
    which traverse the valley.''',

    "text2": '''At the base of Fossil Butte are the bright
    red, purple, yellow and gray beds of the Wasatch
    Formation. Eroded portions of these horizontal
    beds slope gradually upward from the valley floor
    and steepen abruptly. Overlying them and extending
    to the top of the butte are the much steeper
    buff-to-white beds of the Green River Formation,
    which are about 300 feet thick.''',

    "text3": '''The monument contains 8198 acres and protects
    a portion of the largest deposit of freshwater fish
    fossils in the world. The richest fossil fish deposits
    are found in multiple limestone layers, which lie some
    100 feet below the top of the butte. The fossils
    represent several varieties of perch, as well as
    other freshwater genera and herring similar to those
    in modern oceans. Other fish such as paddlefish,
    garpike and stingray are also present.'''
}

data = {'bob': '123', 'ann': 'pass123', 'mike': 'password123', 'liz': "pass123"}

flag = False
qty_try = 3
logged_user = None

while qty_try:
    qty_try -= 1
    username = input("Login")
    password = input("Password")

    if data.get(username) == password:
        flag = True
        logged_user = username
        break
    elif qty_try != 0:
        print(f"Try again, you have {qty_try} attempts!")

if flag:
    print(f"Welcome to the app, {logged_user}")
    print("We have 3 texts to be analyzed.")
else:
    print("unregistered user, terminating the program..")
    exit()

choice = input("Choose text (1, 2 nebo 3): ")

if choice in ["1", "2", "3"]:
    print(f"Enter a number btw. 1 and 3 to select: {choice}")
    text = TEXTS[f"text{choice}"]
else:
    print("It was a bad choice! Terminating the program.")
    exit()

count_words = len(re.findall(r'\b[a-zA-Z]+\b', text))

count_titlecase = len(re.findall(r'\b[A-Z][a-z]+\b', text))

count_uppercase = len(re.findall(r'\b[A-Z]{2,}\b', text))

count_lowercase = len(re.findall(r'\b[a-z]+\b', text))

count_numbers = len(re.findall(r'\d+', text))

sum_numbers = sum(map(int, re.findall(r'\d+', text)))

print(f"\n Results number {choice}:\n")
print(f"There are {count_words} words in the selected text.") 
print(f"There are {count_titlecase} titlecase words.")
print(f"There are {count_uppercase} uppercase words.")
print(f"There are {count_lowercase} lowercase words.")
print(f"There are {count_numbers} numeric strings.")
print(f"The sum of all the numbers {sum_numbers}")


word_lengths = [len(word) for word in re.findall(r'\b\w+\b', text)]
length_freq = {}

for length in word_lengths:
    length_freq[length] = length_freq.get(length, 0) + 1

print("\nLEN|  OCCURENCES       |NR.")
print("-" * 40)
for length in sorted(length_freq):
    stars = '*' * length_freq[length]
    print(f"{length:3}|{stars:<18}|{length_freq[length]}")