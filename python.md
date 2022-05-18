## Arithmetic operators:
| Operations |   Operators   | 
| -------- | ---------- | 
| add      |     +      | 
| subtract |     -      |
| divide   |     /      |
| modulo   |     %      |
| multiplication |     *      |
| Exponentiation |     **     |
| floor division |     //     |

## Limits
maximum call stack is 1000

## array slicing:
A new array is created every time you slice an array

## build-in functions
### string format
```
print("Misha %s and %s around"%('walked',100))
```

### sort()
#### numbers
```
prime_numbers = [11, 3, 7, 5, 2]

# sorting the list in ascending order
prime_numbers.sort()

print(prime_numbers)

# Output: [2, 3, 5, 7, 11]

# Output: [2, 3, 5, 7, 11]
```
#### tuples
```
# random list
random = [(2, 2), (3, 4), (4, 1), (1, 3)]

# sort list with key
random.sort(key=lambda x: x[1])

# print list
print('Sorted list:', random)
```
#### dictionaries
```
# sorting using custom key
employees = [
    {'Name': 'Alan Turing', 'age': 25, 'salary': 10000},
    {'Name': 'Sharon Lin', 'age': 30, 'salary': 8000},
    {'Name': 'John Hopkins', 'age': 18, 'salary': 1000},
    {'Name': 'Mikhail Tal', 'age': 40, 'salary': 15000},
]
employees.sort(key=lambda x: x['Name'])
print(employees, end='\n\n')
```
