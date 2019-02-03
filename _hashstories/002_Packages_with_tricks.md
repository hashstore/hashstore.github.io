---
story_num: 2
title: Packages with tricks
---

# Explore packages with tricks

Let's say we have text with same mistake repeated multiple times. We want to find all occurences of mistake and replace it with correct fragment.  Somebody suggessted to use to check `re` module.

Let try to figure it out. What we can learn about `re`:

```python
>>> dir()
['__annotations__', '__builtins__', '__doc__', '__loader__', '__name__', 
 '__package__', '__spec__']
>>> import re
>>> dir()
['__annotations__', '__builtins__', '__doc__', '__loader__', '__name__',
 '__package__', '__spec__', 're']
>>> type(re)
<class 'module'>
>>>
```

So `import re`, creates `re` variable in current namespace. It points to module object.

Let's see that is inside.

```python
>>> dir(re)
['A', 'ASCII', 'DEBUG', 'DOTALL', 'I', 'IGNORECASE', 'L', 'LOCALE', 'M',
 'MULTILINE', 'Match', 'Pattern', 'RegexFlag', 'S', 'Scanner', 'T',
 'TEMPLATE', 'U', 'UNICODE', 'VERBOSE', 'X', '_MAXCACHE', '__all__',
 '__builtins__', '__cached__', '__doc__', '__file__', '__loader__', 
 '__name__', '__package__', '__spec__', '__version__', '_cache', 
 '_compile', '_compile_repl', '_expand', '_locale', '_pickle', 
 '_special_chars_map', '_subx', 'compile', 'copyreg', 'enum', 
 'error', 'escape', 'findall', 'finditer', 'fullmatch', 'functools', 
 'match', 'purge', 'search', 'split', 'sre_compile', 'sre_parse', 
 'sub', 'subn', 'template']
>>>
```

That's a lot stuff. How can we make sence of it?

Built-in `help` function can clear this up. If we call `help(help)`, it describes itself as:

|  Calling help(thing) prints help for the python object 'thing'.

Help content coulbe quite long and on unix `help()` uses [less](https://ss64.com/bash/less.html) to page thru help content. 

```
Useful `less` commands:
    arrow keys - navigate thru text
    ESC <      - move to begining of document
    ESC >      - move to the end of document
    /PATTERN   - search for PATTERN in text
    q or :q    - exit less
```

Ok, let's invoke `help(re)` and try to find 'replace' in text. After typing `/replace` and reposition to see begining of description.

You should see something like:

![help(re) then /replace](/assets/help_re_search_for_replace.png)

It is sounds like `sub()` is something we can work with. Let's get more information on it:

```python
>>> help(re.sub)
```

```
Help on function sub in module re:

sub(pattern, repl, string, count=0, flags=0)
    Return the string obtained by replacing the leftmost
    non-overlapping occurrences of the pattern in string by the
    replacement repl.  repl can be either a string or a callable;
    if a string, backslash escapes in it are processed.  If it is
    a callable, it's passed the Match object and must return
    a replacement string to be used.
(END)
```

## Put it to the test

Lets create some text and lets play with `re.sub()` to make sure we undestood documentaion:

```python
>>> text="""
...    In another moment down went alice after
... it, never once considering how in the world
... she was to get out again.
...    The rabbit-hole went straight on like a
... tunnel for some way, and then dipped suddenly
... down, so suddenly that alice had not a moment
... to think about stopping herself before she found
... herself falling down what seemed to be a very
... deep well.
... """
>>> fixed=re.sub('alice','Alice',text)
>>>
```

We created `text` variable using triple-quote because we have bunch of new line breaks and we want to preserve them in the variable. As documentation suggest we called `re.sub(pattern, replacement, text)` and store result in `fixed` variable. 

```python
>>> fixed
'\n   In another moment down went Alice after\nit, never once considering how in the world\nshe was to get out again.\n   The rabbit-hole went straight on like a\ntunnel for some way, and then dipped suddenly\ndown, so suddenly that Alice had not a moment\nto think about stopping herself before she found\nherself falling down what seemed to be a very\ndeep well.\n'
>>>
```

Interesting that when we try display it, we dont see line breaks anymore. Python REPL display strings using single quotes and then it has to preserve new line characters in slightly different way than triple quotes can. 

It uses  backslash '\' in combination with 'n' to describe new line character. Such combination called escape sequence and backslash is called escape character. Most common escape sequences are: '\\\\' which is resolved as single backslash, '\n' - as end of line character. You can learn more about [escape sequences from documentation](https://docs.python.org/3/reference/lexical_analysis.html#string-and-bytes-literals).

We can use `print()` funcion to force REPL to dispaly end of lines:
```
>>> print(fixed)

   In another moment down went Alice after
it, never once considering how in the world
she was to get out again.
   The rabbit-hole went straight on like a
tunnel for some way, and then dipped suddenly
down, so suddenly that Alice had not a moment
to think about stopping herself before she found
herself falling down what seemed to be a very
deep well.

```

## Batteries Included

Python come with very rich standart library, and all that functionalty just one `import` away. You can do a lot with just  standart library without need to install any external packages.

Even bits of wistom:
```python
>>> import this
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```

And bit of humor:

```python
>>> import antigravity
>>>
```

![python antigravity](https://imgs.xkcd.com/comics/python.png)

Beyound standart library you can easy install extraodianry number of community supported packages from [Python Package Index - pypi.org](https://pypi.org). All you need is to find package, and type `python -m pip install <package_name>` in shell.
