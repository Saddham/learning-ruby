# Variables
| Variable Scope  | Variable Declaration |
| ------------- | ------------- |
| Global  | $variable  |
| Class  | @@variable  |
| Instance  | @variable  |
| Local  | variable  |
| Block  | variable  |

# Type of Ruby Object Types
## Numbers
### Integers
Class => `Integer`.  
**Methods**
  - Check var class => 1234.class => `Integer` 
  - 100.next => Returns next num
  - -50.abs => absolute value
  - many more
### Floats
Class => `Float`  
**Methods**
- Check var class => 1234.0.class => `Float`
- Float to integer => 0.66.to_i => 0
- Integer to float => 1.to_f => 1.0
- abs, round, ceil etc.
## Strings
### Cancatenation
**Addition Operator**
```
greeting = "Hello"
target = 'World'

greeting + ' ' + target
# Hello World
```
**Apend Operator**
```
greeting = "Hello"
greeting << ' '
greeting << 'World'
# Hello World
```
**Multiplication Operator**
```
a3 = "a" * 3
# aaa
```
**Other Helpful Methods**
```
1.to_s
# "1"

"1".to_i
# 1

"Hello".reverse
# olleH

"hello".capitalize
# Hello

"hello".upcase
# HELLO

"HELLO".downcase
# hello

"HELLO".downcase.capitalize
# Hello

"HELLO".length
# 5
```
**Escaping**
<br>
Use escape charater `\` to escape special chars

Escaping Quotes
```
"Let's escape!" # => Ok
'Let's escape!' # => Not Ok
'Let\'s escape!' # => Ok
```
Escaping Control Characters - only works with strings delimited by double quotes
```
"\ta\n\t\tc"
#	a
#		c
```
Interpolation - using variable expressions inside strings - works only with double quotes
```
name = 'Saddham'
"My name is #{name.upcase}"
# My name is SADDHAM
```
## Arrays
- Dynamic
- Object types can be mixed
```
empty_arr = []
my_arr = [1, 2, 3, '4']

my_arr[4]
# nil

my_arr[4] = 5
# [1, 2, 3, '4', 5]

my_arr << 6
# [1, 2, 3, '4', 5, 6]

my_arr << ['7', 8]
# [1, 2, 3, '4', 5, 6, '7', 8]

my_arr[-1]
# 8

my_arr[-3, 2]
# [6, '7']

my_arr[1..3]
# [1, 2, 3, '4']

my_arr[-3..-1]
# [6, '7', 8]
```
**Array Methods**
```
arr = [2, 4, ['a', 'b'], nil, 4, 'c']

arr.length
# 6

arr.size
# 6

arr.reverse # immutable operation
['c', 4, nil, ['a', 'b'], 4, 2]

arr.reverse! # mutable operation, changes orig arr, effect of using exclamation mark, applies to any other method
# ['c', 4, nil, ['a', 'b'], 4, 2]

arr.shuffle
# Orig array any any order

arr.uniq!
# ['c', 4, nil, ['a', 'b'], 2]

arr.compact!
# ['c', 4, ['a', 'b'], 2] (removes nils)

arr.flatten!
# ['c', 4, 'a', 'b', 2]

arr.include?(2)
# true

arr.delete_at(1)
# 4

arr.delete('c')
# ['a', 'b', 2]

arr.join(',')
# a,b,2

arr.join
# ab2

"ab2".split(",")
# ['a', 'b', '2']

arr.push(4)
# ['a', 'b', 2, 4]

arr.pop()
# ['a', 'b', 2]

arr.unshift('z')
# ['z', 'a', 'b', 2]

arr.shift()
# ['a', 'b', 2]

[1, 2, 3] + [4, 5, 6]
# [1, 2, 3, 4, 5, 6]

[1, 2, 3] - [2]
# [1, 3]
```
