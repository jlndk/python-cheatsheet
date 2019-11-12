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