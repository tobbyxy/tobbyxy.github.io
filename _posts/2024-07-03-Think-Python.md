---
layout: post
title: Think Python by Allen Downey?
date: 2024-07-03 21:01:00
description: 
tags: Python
categories: projects
thumbnail: 
---


# List

## Exercise
Two words are anagrams if you can rearrange the letters from one to spell the other. For example, tops is an anagram of stop.
One way to check whether two words are anagrams is to sort the letters in both words. If the lists of sorted letters are the same, the words are anagrams.
Write a function called is_anagram that takes two strings and returns True if they are anagrams.
Using your function and the word list, find all the anagrams of takes.


```Python
def is_anagram(s1, s2):
    return sorted(s1) == sorted(s2)
```

A palindrome is a word that is spelled the same backward and forward, like “noon” and “rotator”.
Write a function called is_palindrome that takes a string argument and returns True if it is a palindrome and False otherwise

```Python
def is_palindrome(s):
    return s == s[::-1]
def is_palindrome(s):
    return s == ''.join(reversed(s))
```

# Dictionary

## Exercise
“Why do keys in Python dictionaries have to be hashable?”

Dictionaries have a method called get that takes a key and a default value. If the key appears in the dictionary, get returns the corresponding value; otherwise it returns the default value. For example, here’s a dictionary that maps from the letters in a string to the number of times they appear.

Use get to write a more concise version of value_counts. You should be able to eliminate the if statement.

```Python
def value_counts(string):
    counter = {}
    for letter in string:
        counter[letter] = counter.get(letter, 0) + 1
    return counter
```
Write a function named has_duplicates that takes a sequence – like a list or string – as a parameter and returns True if there is any element that appears in the sequence more than once.

```Python
def has_duplicates(s):
    return len(set(s)) < len(s)
#example
has_duplicates('hello')
```

Write function called find_repeats that takes a dictionary that maps from each key to a counter, like the result from value_counts. It should loop through the dictionary and return a list of keys that have counts greater than 1. You can use the following outline to get started.

```Python
def find_repeated(counter):
    return [item for item in counter if counter[item] == 1]
```

