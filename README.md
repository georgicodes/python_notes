# Python
Notes made whilst reading Learning Python 5th Edition.

# Part 1 Getting Started

## Byte Code Compliation
When you execute a program, Python first compiles your source code into byte code.

Compilation is a translation step and byte code is a lower-level platform-independent representation of your source code.

Python translates each of your source statements into a group of byte code instructions by decomposing them into individual steps.

This byte code translation step is done to speed execution as byte code can be run much more quickly than original source statements.

Byte code will be saved to files with the `.pyc` extension in a folder called `_pycache_` located in the directory where your source files reside.

This is done to speed up startup times. Source code changes will trigger a new compliation.

If python doesn't have access to write to tyour file system, the `.pyc` files are stored in memory instead but this isn't optimal. 

When you ship python code you could just ship the `.pyc` files and python will happily run the program.

Byte code is only saved in files for files that are imported.

NOTE: byte code is not machine code (eg for an Intel chip). Byte code is a Python specific representation. The PVM loop not the CPU chip must interpret the byte code and byte code instructions require more work than CPU instructions.

## Python Virtual Machine
The PVM is a code loop that iterates over each of the bye code instructions to carry out their operations.

## CPython
CPython is the original and standard implementation of Python.

## Shebang
You can make a script executable by doing two things:

1. Adding a Shebang / Hash bang
```py
#!/usr/local/bin/python
print('The Bright Side ' + 'of Life...')
```
2. Making the script have executable privileges
```
chmod +x brian.py
```

The special line at the top of the file tells the system where the Python interpreter lives. It’s special on Unix because the operating system shell uses it to find an interpreter for running the program code in the rest of the file.

The script can now be simply run as:
```
$ brian
```

## Module Imports
Every file in python is a module. This module-based services model is the core idea behind program architecture in python.

One of the modules gets designated as the `top-level` file or `script` - this is the file that launches the program.

When a module is imported the code in the file is run. Each module is its own namespace.

To reload a script if you have changed the imported module in a REPL then you will need to call `reload`
```py
from imp import reload 
reload(script)
```

To list all attributes in a module run
```py
dir(myModule) 
# which returns
['__builtins__', '__doc__', '__file__', '__name__', '__package__', 'a', 'b', 'c']
```


