# Strings

## Transformation
```python
# Lowercase
str.lower() # hello world
# Uppercase
str.upper() # HELLO WORLD
# Capitalize (first letter of string upper, rest lower)
str.capitalize() # Hello world
# Title case (first letter of each word upper, rest lower)
str.title() # Hello World
# Swap case (reverses case of each letter)
str.swap() # hELLO wORLD
```
## Search
```python
#does string contain substring?
str.find("foo", [beg=0, end=len(str)])
# same as find, but raises an exception if substring not found
str.index("foo", [beg=0, end=len(str)])
# if string starts with substring
str.startswith("foo", [beg=0, end=len(str)])
# if string ends with substring
str.endswith("foo", [beg=0, end=len(str)])
# count how many times substring occours in string
str.count("foo", [beg=0, end=len(str)])
```
## Character classifiers
```python
# Returns true if string has at least 1 character and all characters are alphanumeric and false otherwise.
str.isalnum()
# Returns true if string has at least 1 character and all characters are alphabetic and false otherwise.
str.isalpha()
# Returns true if string contains only digits and false otherwise.
str.isdigit()
# Returns true if string has at least 1 cased character and all cased characters are in lowercase and false otherwise.
str.islower()
# Returns true if a unicode string contains only numeric characters and false otherwise.
str.isnumeric()
# Returns true if string contains only whitespace characters and false otherwise.
str.isspace()
# Returns true if string is properly "titlecased" and false otherwise.
str.istitle()
# Returns true if string has at least one cased character and all cased characters are in uppercase and false otherwise.
str.isupper()
# Returns true if a unicode string contains only decimal characters and false otherwise.
str.isdecimal()
```
## Formatting
```python
# Basic formatting
price = 49
txt = "The price is {} dollars"
print(txt.format(price))

# Format the price to be displayed as a number with two decimals:
txt = "The price is {:.2f} dollars".format(price)

# indexed formatting
quantity = 3
itemno = 567
price = 49
myorder = "I want {0} pieces of item number {1} for {2:.2f} dollars."
print(myorder.format(quantity, itemno, price))

#named indicies
myorder = "I have a {carname}, it is a {model}."
print(myorder.format(carname = "Ford", model = "Mustang"))
```

## Character and ASCII

```python
# Get ASCII code of character
ord('A') #65
# Get character from ASCII code
chr(97) #'a'
```