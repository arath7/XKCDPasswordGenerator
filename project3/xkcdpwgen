#!/usr/bin/env python3

import argparse
import random

parser = argparse.ArgumentParser()

parser.add_argument('-w', '--words', type=int, default=4,
                    help='include WORDS words in the password (default=4)')

parser.add_argument('-c', '--caps', type=int, default=0,
                    help='capitalize the first letter of CAPS random words (default=0)')

parser.add_argument('-n', '--numbers', type=int, default=0,
                    help='insert NUMBERS random numbers in the password (default=0)')

parser.add_argument('-s', '--symbols', type=int, default=0,
                    help='insert SYMBOLS random symbols in the password (default=0)')

args = parser.parse_args()


# returns a random word from a list of words
def random_word():
    randomword = open('words.txt').read().splitlines()
    return random.choice(randomword)


# list of possible numbers to be inserted
def random_num():
    randomnumbers = ["1", "2", "3", "4", "5", "6", "7", "8", "9", "0"]
    return random.choice(randomnumbers)

# list of possible symbols to be inserted
def random_symb():
    randomsymbols = ["~", "!", "@", "#", "$", "%", "^", "&", "*", ".", ":", ";"]
    return random.choice(randomsymbols)


password = []
# for capitalizing words in password list
for i in range(0, args.words):
    if args.caps > 0:
        password.append(random_word().upper())
        args.caps -= 1
    else:
        password.append(random_word())

# for adding numbers to password list
for i in range(0, args.numbers):
    password.append(random_num())

# for adding symbols to the password list
for i in range(0, args.symbols):
    password.append(random_symb())

# randomizes the elements of the list
random.shuffle(password)

# prints a concatenated password
print("".join(password))
