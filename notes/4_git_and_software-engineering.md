# Git and software engineering

## Software engineering best practices 
Tutor - Shehab Abdel-Salem

### Best practice
- Functional 
- Maintable - even if it is functional it still neds to be written in a way that it is easy to re-write
- Reliable - Should provide same functionality despite the format, for example. 
- Readable - Even if the code does the purpose just fine, it needs to be clear, otherwise other people can't understand it.
- Testable - writing software in a way thatis modular helps us to test it. 

### Convention - PEP8 
- Keep functions and methods short 
- Don't abbreviate, we all have auto-complete - not important to be short, needs to be descriptive.
- No global variables 
- Modular code 
- Good coomments - don't explain the code, explain the purpose/reason/why
- Naming conventions
- Function and metho annotation (type hints)
- Easier to ask for forgiveness thatn permission (eafp) vs look before you leap (lbyl) - these are mechanisms of how you can write code. 

### Naming conventions 
- Use verbs for methods 
- Use nounds for variables 
- Use questions for booleans -- is_*

- Use snake_case for functions / methods / variables 
- Use CamelCase for classes  - capitalise all letters of achronym
- Use UPPER_CASE for global constants

### Type hinting 
- Python is dynamically types not statically typed 
- This means types are picked up at run time and we do not need to specify type 
- We should therefore specify type to ohelp the user / improve documentation 
- We should also hint at variable types

### LBYL
- If this file exists, then open it. 
- If that row exists, act on it. 
- This is not pythonic 

if conditions:
    ... 
    return <answer>
else: 
    print("Error: ...")
    return None

### EAFP
- Catch errors if there are exceptions
try: 
    ...
except ZeroDivisonError:
    print("Error: ...")
    return None 

