---
story_num: 1
title: Powerful Reptile
---

# Powerful Reptile

This powerful reptile is called Python. It lives [](http://python.org). You may already have it on your computer but if you dont it is easy to get it. 

## Why it is so powerful

Anybody can use python because it free. It is easy to teach computer new tricks using python, and a lot of people do and share it with community. Python stores new tricks in packages, people share them and community ensure that only best packages become widely known. So power of python mulitpies.

## Let's try it


Call python. If you see something like bellow you have python installed, (TODO install instructions ...)

```python
$ python
Python 3.7.0 (default, Jun 28 2018, 07:39:16) 
[Clang 4.0.1 (tags/RELEASE_401/final)] :: Anaconda, Inc. on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>  
```

You just run python in REPL (read-eval-print loop) mode. It is when python wait from you one command at the time (read), executes it (eval), print result and repeat.

How can I exit from that loop you may ask. You just simply call command `quit()` and you out.

>>> Shortcut: To exit on windows you can use: Ctrl+Z then ENTER . On unix Ctrl+D will take you out of the loop.

## Calculator

You can do calculation in python:

```python
>>> 3+5
8
>>> x=7
>>> 3*x
21
>>>  
```

store results in variables like `x`

## Working with text

Assign string, join strings, repeate strings:

```python
>>> s='hello '
>>> s
'hello '
>>> s + 'world!'
'hello world!'
>>> 'z' * 5
'zzzzz'
>>> 
```

## Inspect what we created

Command `dir()` allow us to see what we have in local context:

```python
>>> dir()
['__annotations__', '__builtins__', '__doc__', '__loader__', '__name__', '__package__', '__spec__', 's', 'x']
>>>
```

We see some service variables along with 2 variables `x` and `s` that we created.
