# Python cheatsheet

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
# Lists and Dictionaries

## Comprehension

```python
# List comprehension
[x for x in list]
# Nested list comprehension
[x for x in y if x % 2 == 0 for y in items if len(y) > 2]
# Dictionary comprehension (list of tuples to dictionary)
{key:value for (key, value) in items}
# Dictionary to list of tuples
[(key, value) for key, value in items]
```

## Sortering

### in-place sorting
```python
# Sorting in-place
items.sort()
# Sort using custom key (can either be lamda or a method ref)
items.sort(key=lambda el: el[0])
# Sort in reverse order
items.sort(reverse=True)
```

### sort into new list
```python
# Sorting into copy of list
sortedItems = sorted(items)
# Sort using custom key (can either be lamda or a method ref)
sortedItems = sorted(items, key=lambda el: el[0])
# Sort in reverse order
sortedItems = sorted(items, reverse=True)
```

## Modification

### Reverse
```python
# in-place
items.reverse()
# creates a copy 
reversedItems = reversed(items)
```

## Slicing
```python
# General notation
a[start:stop:step]  # start through not past stop, by step

# Simple examples
a[start:stop]       # items start through stop-1
a[start:]           # items start through the rest of the array
a[:stop]            # items from the beginning through stop-1
a[:]                # a copy of the whole array

# Negative examples
a[-1]               # last item in the array
a[-2:]              # last two items in the array
a[:-2]              # everything except the last two items

#Step examples
a[::-1]             # all items in the array, reversed
a[1::-1]            # the first two items, reversed
a[:-3:-1]           # the last two items, reversed
a[-3::-1]           # everything except the last two items, reversed
```

## Iterables

### Enumerate
```python
# Enumerate over an iterable with a corresponding index
enumerate(iterable, [start=0])

# Basic example
words = ["foo", "bar", "baz"]

for i, word in enumerate(words):
    print(i, word)  # prints (0, foo)
                    #        (1, bar)
                    #        (2, baz)

# Alternativly an offset can be given
for i, word in enumerate(words, 42):
    print(i, word)  # prints (42, foo)
                    #        (43, bar)
                    #        (44, baz)
```

### Zip

```python
# Returns an iterator of tuples, where the i-th tuple contains the i-th element from each of the argument sequences or iterables.
zip(*iterables)

# Iterate over two corresponding lists
students = ["Jacob", "Poppy", "Jonas"]
coolnesses = [10, 10, 10**8]

for student, coolness in zip(students, coolnesses):
    print(student, coolness)
    # prints Jacob 10
    #        Poppy 10
    #        Jonas 100000000

# Iterate over three corresponding lists

acronyms = [
    "Analysis, Design and Software Architecture",
    "Mobile and Distributed Systems",
    "Introduction to Database Design"
]
subjects = ["BDSA", "MODIS", "IDD"]
ectses = [15,7.5,7.5]
for acronym, subject, ects in zip(acronyms, subjects, ectses):
    print(acronym, subject, ects)
    # prints Analysis, Design... 15  BDSA
    #        Mobile and Distr... 7.5 MODIS
    #        Introduction to ... 7.5 IDD
```







# Templates
## Input readers

```python
# read n lines using for loop
cases = int(input())
for i in range(cases):
    #code

#read n lines using list comprehension
n = int(input())
cases = [input() for x in range(n)]

# while not 0 0
line = input()
while line != "0 0":
    #code
    line = input()

#until end of file
import sys
for line in sys.stdin:
    line = line.strip() #remove those pesky newline characters
    #code

#assign numbers on line to ints
a, b, c = map(int, input().split(" "))
```

## Algorithms
### BFS - Breadth first search (with lazy construction of graph)
```python
#bfs
def generateOptions(origin):
    result = []
    #add options to result
    return result


start = "" #starting value
goal = "goal" #goal value
fromMap = {start:start}
used = set()
while goal not in fromMap:
    currentList = [x for x in fromMap if x not in used]
    for item in currentList:
        for subItem in generateOptions(item):
            if subItem not in fromMap:
                fromMap[subItem] = item
        used.add(item)
path = [goal]
current = goal
while current != start:
    current = fromMap[current]
    path.append(current)
path.reverse()
# path is now a the sortest list of verticies from start to goal
```

### Dijkstra
```python
from collections import defaultdict
import math

class Graph:
    def __init__(self):
        self.nodes = set()
        self.edges = defaultdict(list)
        self.distances = {}

    def add_node(self, value):
        self.nodes.add(value)

    def add_edge(self, from_node, to_node, distance,):
        self.edges[from_node].append(to_node)
        self.edges[to_node].append(from_node)
        self.distances[(from_node, to_node)] = distance


def dijsktra(graph, initial):
    visited = {initial: 0}
    path = {}
    nodes = set(graph.nodes)

    while nodes:
        min_node = min(nodes, key=lambda x: visited.get(x, math.inf))
        if min_node is None:
            break
        nodes.remove(min_node)
        current_weight = visited[min_node]

        for edge in graph.edges[min_node]:
            weight = current_weight + graph.distances[(min_node, edge)]
            if edge not in visited or weight < visited[edge]:
                visited[edge] = weight
                path[edge] = min_node

    return (visited, path)
```
