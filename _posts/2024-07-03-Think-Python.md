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
