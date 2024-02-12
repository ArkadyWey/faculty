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

### SWE Best practice 
- Use versioning system - can also use thigs like .bashrc
- Test driven development (TDD) - think about how you are going to test first, and try to break the code in the test
- Refactor - modify code without changign functionality or purposes / changing structure or naming... 'cleaning up'. This should be included in team's general work flow.
- DRY (don't repeat yourself) - don't copy and paste code, you're doing something wrong if you do.
- KISS (keep is simple, stupid)
- YAGNI (you aren't gonna need it) - only write the things tht you need right now.

### SOLID principles 
- Every letter refers to a design patten 
- Related to object oriente programming 
- How things should interact with each other in classes. 

### Pragmatic 
- Code doesn't have to be perfect at the time 
- Early optimisation is sometimes a waste of time because the functionality changes over time 

### Object Oriented Programming (OOP)
- Abstraction -  allows information hiding and exposing essential features to users.
- Encapsulation - bundle data and methods that are connected in the same unit. Protects data from outside interference. 
- Inheritance - allows a class (subclass) to inherit properties from another class (Superclass), which facilitates code re-use.
- Polymorphism - allows objects of differnt classes to be treated as objects of a common superclass, enabling flexibility and extensibility in method invocation. 
# TODO: ?

### Inheritance 
- Introduces strong coupling - inheritance tax -- whatever you do in the superclass affects the subclass.
- Inheritance is good to model an 'is-a' relationship ... student IS A person - don't use it unless you have this relarionoship. 
- Composition models the 'has-a' relationship .. car HAS A a wheel.

## 3. Python for data science
Michael Keeling 

## 4. Probabilistic reasoning 
Erick Hinds Mingo 

- We should use probability theory to hedge against bias 
- We are looking to overcome the fear of obvious answers 





