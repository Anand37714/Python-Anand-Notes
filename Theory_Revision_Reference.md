# Python Theory Revision — Complete Reference
## From Logic Basics to Modular Code II

---

# 1. DATA TYPES

| Type | Example | Notes |
|---|---|---|
| `int` | `85000` | Whole number |
| `float` | `10.5` | Decimal number |
| `bool` | `True` / `False` | Only two values |
| `None` | `None` | Represents nothing |
| `str` | `"Laptop"` | Text in quotes |

```python
price      = 85000        # int
discount   = 10.5         # float
in_stock   = True         # bool
offer      = None         # None
name       = "Laptop"     # str

print(type(price))        # <class 'int'>
print(id(price))          # memory address
```

---

# 2. OPERATORS

## Arithmetic
| Operator | What it does | Example |
|---|---|---|
| `+` | Add | `1500 + 800` |
| `-` | Subtract | `85000 - 8500` |
| `*` | Multiply | `1500 * 2` |
| `/` | Divide | `85000 / 2` |
| `//` | Floor divide | `85000 // 3` |
| `%` | Remainder | `10 % 3` |
| `**` | Power | `2 ** 10` |

## Comparison
| Operator | Meaning |
|---|---|
| `==` | equal to |
| `!=` | not equal to |
| `>` | greater than |
| `<` | less than |
| `>=` | greater than or equal |
| `<=` | less than or equal |

## Logical
| Operator | Meaning |
|---|---|
| `and` | both must be True |
| `or` | at least one must be True |
| `not` | reverses True/False |

---

# 3. INPUT AND OUTPUT

```python
# input() always returns a string
name = input("Enter name: ")

# Type casting
age    = int(input("Enter age: "))
price  = float(input("Enter price: "))

# f-string formatting
amount = 85000
print(f"Price: Rs.{amount:,}")        # Rs.85,000
print(f"Price: Rs.{amount:,.2f}")     # Rs.85,000.00
print(f"{'Item':<10} {'Price':>10}")  # left and right align
```

---

# 4. LISTS

**Ordered, mutable, allows duplicates**

```python
products = ["Mobile", "Laptop", "Tablet","Mobile"]
values = ["Mouse","Bottle","Computer"]

# Indexing
products[0]     # Mobile
products[-1]    # Tablet

# Slicing [start:stop:step]
products[:]     # ["Mobile", "Laptop", "Tablet"]
products[:2]    # ["Mobile", "Laptop"]
products[::2]   # ["Mobile", "Tablet"]
products[::-1]  # reversed
```

## List Methods — Return Types
| Method | Returns |
|---|---|
| `.append()` | None |
| `.insert()` | None |
| `.extend()` | None |
| `.remove()` | None |
| `.pop()` | Removed item |
| `.sort()` | None |
| `.copy()` | New list |
| `.clear()` | None |
| `.index()` | Integer |
| `.count()` | Integer |

---

# 5. TUPLES

**Ordered, immutable, allows duplicates**

```python
order = ("ORD001", "Laptop", 85000)

# Access same as list
order[0]    # ORD001

# Cannot change
order[0] = "ORD002"    # TypeError

# Packing and unpacking
order = 1,2,3,4
order_id, product, price = order

# Ignore values
_, product, _ = order

#Multiple Values packing
order = 1,2,3,7,8,9
order_id,*product,price=order
```

## Tuple Methods
| Method | Returns |
|---|---|
| `.count()` | Integer |
| `.index()` | Integer |

---

# 6. SETS

**Unordered, mutable, NO duplicates, Immutable elemets are allowed as set elements**

```python
# Create
blood_groups = {"A+", "B+", "O+"}

# Empty set — must use set()
empty = set()    # NOT {}

# Duplicates removed automatically
items = set(["A+", "B+", "A+"])    # {"A+", "B+"}
```

## Set Operations
| Operation | Symbol | Method |
|---|---|---|
| Union | `\|` | `.union()` |
| Intersection | `&` | `.intersection()` |
| Difference | `-` | `.difference()` |
| Symmetric Difference | `^` | `.symmetric_difference()` |

## Hashability
- Immutable types (str, int, tuple) → hashable → allowed in set
- Mutable types (list, dict, set) → not hashable → NOT allowed

---

# 7. DICTIONARIES

**Key-value pairs, ordered (Python 3.7+), mutable**

```python
product = {
    "name" : "Laptop",
    "price": 85000
}

# Access
product["name"]                    # direct — KeyError if missing
product.get("name")                # safe — None if missing
product.get("brand", "Unknown")    # safe — default if missing
```

## Dictionary Methods — Return Types
| Method | Returns |
|---|---|
| `.get()` | Value, None, or default |
| `.keys()` | dict_keys view |
| `.values()` | dict_values view |
| `.items()` | dict_items view |
| `.update()` | None |
| `.pop()` | Removed value |
| `.copy()` | New dictionary |
| `.clear()` | None |

---

# 8. NESTED STRUCTURES

```python
# List of Dicts — rows of data
patients = [{"id": "P001", "ward": "ICU"}, {"id": "P002", "ward": "General"}]
patients[0]["ward"]    # ICU

# Dict of Lists — grouped data
depts = {"Cardiology": ["Dr. A", "Dr. B"]}
depts["Cardiology"][0]    # Dr. A

# Nested Dict — sub-sections
hospital = {"icu": {"beds": 20, "occupied": 15}}
hospital["icu"]["beds"]    # 20
```

---

# 9. STRINGS

**Ordered, immutable, allows duplicates**

## Key Methods — Syntax and Returns
| Method | Syntax | Returns |
|---|---|---|
| `.upper()` | `str.upper()` | New string |
| `.lower()` | `str.lower()` | New string |
| `.strip()` | `str.strip(chars='')` | New string |
| `.replace()` | `str.replace(old, new, count=-1)` | New string |
| `.split()` | `str.split(sep=None, maxsplit=-1)` | List |
| `.join()` | `str.join(iterable)` | New string |
| `.find()` | `str.find(sub, start=0, end=len)` | Integer or -1 |
| `.index()` | `str.index(sub, start=0, end=len)` | Integer or ValueError |
| `.count()` | `str.count(sub, start=0, end=len)` | Integer |
| `.startswith()` | `str.startswith(prefix)` | Boolean |
| `.endswith()` | `str.endswith(suffix)` | Boolean |
| `.isdigit()` | `str.isdigit()` | Boolean | "45"|
| `.isalpha()` | `str.isalpha()` | Boolean | "lagos"|
|"45lagos" - `isalnum()`|
| `.zfill()` | `str.zfill(width)` | New string |
| `.center()` | `str.center(width, fillchar=' ')` | New string |

> Strings are immutable — methods return new strings, never modify original

---

# 10. CONTROL FLOW

## Indentation Rule
> Any line ending with `:` — the next line must be indented 4 spaces

## Truthy and Falsy
| Falsy | Truthy |
|---|---|
| `0` | Any non-zero number |
| `""` | Non-empty string |
| `[]` | Non-empty list |
| `None` | Anything with content |
| `False` | `True` |
1,giraffe,{8,9,10},[6,7,5],(1,2,3),{"time":7} --> True Values

## Conditionals
```python
if condition:
    pass
elif condition:
    pass
else:
    pass
```

## Ternary
```python
value = "Yes" if condition else "No"
```

## match-case (Python 3.10+)
```python
match variable:
    case "value1":
        pass
    case "value2":
        pass
    case _:    # default
        pass
```

> match-case is for exact value matching only — use if-elif for ranges

---

# 11. LOOPS I

## For Loop
```python
for variable in iterable:
    # runs once per item
```

**Iterables:** list, string, dict, tuple, set, range

```python
# range(start, stop, step)
for i in range(1, 11):      # 1 to 10
    pass

for i in range(10, 0, -1):  # countdown
    pass

# enumerate — index + value
for i, item in enumerate(products):
    pass

# dict iteration
for key in d:               # keys
for value in d.values():    # values
for key, value in d.items():# both
```

## While Loop
```python
while condition:
    # runs while condition is True
    # must update condition — otherwise infinite loop
```

## Control Keywords
| Keyword | What it does | Loop continues? |
|---|---|---|
| `break` | Exits loop entirely | No |
| `continue` | Skips current iteration | Yes |
| `pass` | Does nothing — placeholder | Yes |

> break and continue only affect the innermost loop

---

# 12. LOOPS II

## List Comprehension
```python
# Transform
[expr for x in iterable]

# Filter
[expr for x in iterable if condition]

# if-else transform — if-else BEFORE for
["Yes" if x > 0 else "No" for x in list]

# Filter — if AFTER for
[x for x in list if x > 0]
```

## Dict Comprehension
```python
{key: value for x in iterable if condition}
```

## Nested Loops
```python
for outer in outer_list:
    for inner in inner_list:
        # runs outer × inner times
```

> break/continue only affect the innermost loop

---

# 13. MODULAR CODE I — FUNCTIONS

## Defining a Function
```python
def function_name(parameters):
    """Docstring."""
    # body
    return value
```

## Argument Types
| Type | Example | Notes |
|---|---|---|
| Positional | `func(1, 2)` | Order matters |
| Keyword | `func(a=1, b=2)` | Order doesn't matter |
| Default | `def f(x, y=10)` | Used if not passed |

## Rules for mixing
- Regular → keyword → default
- Default args must come after non-default

## Return Values
```python
# Single value
return value

# Multiple values — packed as tuple
return a, b, c

# Unpack on call
x, y, z = function()
```

## print vs return
| | print | return |
|---|---|---|
| Shows on screen | Yes | No |
| Sends value back | No | Yes |
| Can store result | No — None | Yes |

## Docstrings — Google Style
```python
def function(param):
    """
    One line description.

    Args:
        param (type): Description

    Returns:
        type: Description
    """
```

---

# 14. MODULAR CODE II

## *args — Variable Positional Arguments
```python
def func(*args):
    # args is a tuple
    for item in args:
        print(item)

func(1, 2, 3, 4, 5)    # any number of args
```

## **kwargs — Variable Keyword Arguments
```python
def func(**kwargs):
    # kwargs is a dict
    for key, value in kwargs.items():
        print(f"{key}: {value}")

func(name="Laptop", price=85000)
```

## Order of Parameters
```
def func(regular, *args, **kwargs)
```

## Lambda
```python
# Syntax
lambda parameters: expression

# Example
double = lambda x: x * 2
```

> Lambda only — one expression, no statements, no loops, no return keyword

## Functional Tools
| Function | What it does | Returns |
|---|---|---|
| `map(func, iter)` | Transform every item | map object |
| `filter(func, iter)` | Keep items where func returns True | filter object |
| `reduce(func, iter)` | Combine all into one value | Single value |

> map() and filter() return lazy objects — wrap in list() to see values
> reduce() needs: `from functools import reduce`

## LEGB Scope Rule
| Letter | Scope | Where |
|---|---|---|
| L | Local | Inside current function |
| E | Enclosing | Inside outer function |
| G | Global | Top level of file |
| B | Built-in | Python's own names |

> Python searches L → E → G → B and uses first match found

```python
# Modify global from inside function
global variable_name

# Modify enclosing from inner function
nonlocal variable_name
```

---

# QUICK REFERENCE — KEY RULES

```markdown
| Rule | Detail |
|---|---|
| Indentation | 4 spaces after every colon |
| Mutable | list, dict, set — can change |
| Immutable | int, float, str, tuple, bool — cannot change |
| Hashable | Immutable types only — can go in sets |
| Iterable | list, str, dict, tuple, set, range |
| map/filter | Lazy — wrap in list() to see values |
| Lambda | One expression only — no statements |
| return None | Every function returns None if no return |
| short circuit | and stops at first False, or stops at first True |
```
