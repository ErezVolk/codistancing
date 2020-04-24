_Codistancing_ is a Python code formatter that makes sure tokens in your code
do not infect each other. By using it, you agree to cede control over the looks 
of your code. In return, _Codistancing_ gives you determinism and extremely 
unreadable code - but at least it is disease free.

## Installation and Usage

### Installation
Just clone this project.

### Usage
```
usage: codistancing.py [-h] [-l] [-c CODE] [-d] [FILE [FILE ...]]

positional arguments:
  FILE                 Files to reformat (in place)

optional arguments:
  -h, --help            show this help message and exit
  -l, --line            Include distancing between lines
  -c CODE, --code CODE  Format the code passed in as a string.
  -d, --dry-run         Do nothing. Really nothing.
```

_Codistancing_ is a well-behaved Unix-style command-line tool:

- it does nothing if no sources are passed to it;
- it only outputs messages to users on standard error;
- exits with code 0 unless an internal error occurred;
- its README file is based on cutting edge formatters.

### Note: This is a stupid product
_Codistancing_ is not used by anyone and no one should probably use it. Also, 
this is a beta product and your code might not run after running


## The _Codistancing_ code style
Basically, add spaces everywhere. This usually do not go well with PEP8.

### Spaces
_Codistancing_ adds four spaces between every two tokens in the same line.
```python
# in:
if (x > y): continue

# out:
if    (    x    >    y    )    :    continue
``` 

### Line length
If this results in lines longer than 80 characters - well, too bad for you.
```python
# in:
one, two, three, four = (1, 2, 3, 4)

# out:
one    ,    two    ,    three    ,    four    =    (    1    ,    2    ,    3    ,    4    )
```

### Empty lines
If the `-line` argument is not passed, spacing between lines remains as it is.
Otherwise, _Codistancing_ makes sure there are two blank lines between every two
content lines.
```python
# in:
if x:
    pass
# out:
if    x    :


    pass

```
The number remains two, even if it means deleting lines.


## Integrations
There are no integrations and I do not plan to add any. This is a stupid tool 
that was created as a joke during CoVID-19 social distancing times. Do yourself
a favor and do not use it if you care about your codebase. Use
[black](https://black.readthedocs.io/en/stable/) instead. 