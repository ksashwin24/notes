# Python
In python, Hash (`#`) indicates a single-line comment.
```python
# This is a single-line comment.
print("x",2,3,"y",5, sep="-", end=".") # This is an in-line comment.
```
```
x-2-3-y-5.
```
# Variables
Variables are labels that can be assigned to values which are stored in a specific location in memory.

Variables can contain letters, numbers and underscores but can't begin with a number and are usually in lowercase with underscores instead of space (`first_variable`, `lunch_time`).

Constant is a variable whose value remains the same throughout the life of a program. Python doesn't have a built-in constant type but programmers use all capital letters to indicate a constant (`MAX_SCORE`).

Assigning multiple variables in a single line and swapping variables are possible due to tuple packing and unpacking.
```python
a=b=1 # Chained Assignment, not due to tuple packing and unpacking.
x,y,z = 1,2,3
print(x,y,z,a,b)

x,y = y,x
print(x,y)
```
```
1 2 3 1 1
2 1
```
# Strings
Anything inside quotes is considered a string
```python
x="heLlo woRLd"
print(x.title())
print(x.lower())
print(x.upper())
```
```
Hello World
hello world
HELLO WORLD
```
f-strings contains replacement fields which allows us to insert variables, expressions and functions within strings.
```python
def square_x(x):
    return x**2
print(f"Hello, {"Lu"+'f'*2+'y'} {square_x(2):.1f}")
```
```
Hello, Luffy 4.0
```
Tabs and newlines inside strings:
```python
print("Languages:\n\tEnglish\tSpanish\n\tFrench\tChinese")
```
```
Languages:
	English	Spanish
	French	Chinese
```
Note: Look at the `\t`(tab) in front of Spanish. It's just a single space. Tabs doesn't mean 8 or 4 white spaces. A tab moves the text to the "tab stop" which are like a set of invisible columns every 8 or 4 characters depending on the text editor or terminal. Most terminal's tab stops are 8 characters apart.

To remove white spaces from a string:
```python
x="   Hello   "
print(x.rstrip()) # only right side
print(x.lstrip()) # only left side
print(x.strip())  # both sides
```
```
   Hello
Hello   
Hello
```
Removing Prefixes and Suffixes:
```python
x='https://www.youtube.com/'
print(x.removeprefix("https://www."))
print(x.removesuffix("/"))

y=x.removeprefix("https://www.")
print(y.removesuffix("/"))
```
```
youtube.com/
https://www.youtube.com
youtube.com
```
Note: String methods leaves the original string unchanged as Strings are immutable (cannot be modified or changed after it is created). To preserve the result, assign it to a new or original variable.
# Numbers
Any number with an exponential notation or a decimal point is a float.

Division of any 2 numbes (integers or floats) always results in a float. Mixing an integer and float in any operation also results in a float.

Underscores can be used to make large numbers more readable
```python
print(2+5, 4*2, 4**2)
print(2.0+5, 4*2.0, 4/2, 2.5**2, 2e2)
print(1_000, 10_00, 100_000, 5_678.984_54)
```
```
7 8 16
7.0 8.0 2.0 6.25 200.0
1000 1000 100000 5678.98454
```
# List
A list is mutable, can hold multiple items in a specific order, including duplicates.

Initializing Lists:
```python
a=[]
b=list() # can convert any iterable to list
print(a,b)
```
```
[] []
```
In python, indices start at 0 and increase by 1 from the start, while negative indices start from the end,  from -1 and decrease by 1.
```python
cars=["bmw", "audi", "benz"]
print(cars[0].upper(), cars[1].title())
print(cars[-1].title(), cars[-3].upper())
cars[-2]="tesla"
print(cars)
```
```
BMW Audi
Benz BMW
['bmw', 'tesla', 'benz']
```
```python
cars=["bmw", "audi"]
cars.append("tesla") # adds to the end of the list
cars.insert(0, "benz") # inserts item before the element at the given index
print(cars)
cars.insert(-2, "ford")
print(cars)
```
```
['benz', 'bmw', 'audi', 'tesla']
['benz', 'bmw', 'ford', 'audi', 'tesla']
```
Removing items from a list:
```python
cars=['benz', 'bmw', 'ford', 'audi', 'tesla', 'pagani']
del cars[2] # deletes the elements at a particular index
print(cars)
x=cars.pop(1) # when you need the removed value
print(x,cars)
cars.remove('tesla') # when you know the value
print(cars)
```
```
['benz', 'bmw', 'audi', 'tesla', 'pagani']
bmw ['benz', 'audi', 'tesla', 'pagani']
['benz', 'audi', 'pagani']
```
Note: `.pop()` when used without arguments removes and returns the last element.
Note: `.remove()` only removes the first match it finds.

Changing the order of a list:
- permanently
```python
cars=['benz', 'bmw', 'ford', 'audi', 'tesla', 'pagani']
cars.reverse()
print(cars)
cars.sort()
print(cars)
cars.sort(reverse=True)
print(cars)
cars.reverse()
print(cars)
```
```
['pagani', 'tesla', 'audi', 'ford', 'bmw', 'benz']
['audi', 'benz', 'bmw', 'ford', 'pagani', 'tesla']
['tesla', 'pagani', 'ford', 'bmw', 'benz', 'audi']
['audi', 'benz', 'bmw', 'ford', 'pagani', 'tesla']
```
- temporarily
```python
cars=['benz', 'bmw', 'ford', 'audi', 'tesla', 'pagani']
print(sorted(cars))
print(cars)
print(sorted(cars, reverse=True))
print(cars)
```
```
['audi', 'benz', 'bmw', 'ford', 'pagani', 'tesla']
['benz', 'bmw', 'ford', 'audi', 'tesla', 'pagani']
['tesla', 'pagani', 'ford', 'bmw', 'benz', 'audi']
['benz', 'bmw', 'ford', 'audi', 'tesla', 'pagani']
```
