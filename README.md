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
## Hashes
An unordered, object-indexed collection of objects (or key-value pairs). Map in Java, dictionary in python
```
car = {
  'brand' => 'Ford',
  'model' => 'Mustang',
  'color' => 'blue',
  'interior_color' => 'tan',
}

car['model']
# Mustang

car['color'] = 'green'
car['color']
# green

car['doors'] = 2
car['doors']
# 2

car.keys
# ['brand', 'doors', 'color', 'interior_color', 'model']

car.to_a
# [['brand', 'Ford'], ['doors', 2], ...]
# array of arrays of key value pairs
```
## Symbols
- Like strings but cannot be edited
- Begin with a colon
- Not delimited by quotes
- Lowercase, underscore, no spaces
- Used for memory optimization. Ruby does not garbase collect them as often as strings
- Symbols and strings are not interchangeable
```
person = {
  :first_name => 'Saddham',
  :last_name => 'Pathan'
}

person[:last_name]
# Pathan

person["first_name"]
# nil
```
### Hash Symbol Shorthand
- Keys are symbol here and not strings
- Cannot use integers as keys
- :100 is not a valid symbol name
```
scores = {low: 2, high: 8, avg: 5}

scores.keys.first.class
# Symbol
```
## Boolean
- Values => true and false
- Classes => `TrueClass` and `FalseClass`
- It is Ruby convention that method names that end in `?` return boolean value
```
true.class
# TrueClass

false.class
# FalseClass

x = 1
x >=100 || x<=50
# true

[1, 2, 3].include?(2)
# true
```
## Ranges
- Inclusive range (two dots): `1..10` => `1, 2, 3,..., 9, 10`
- Exclusive range (three dots): `1...10` => `1, 2, 3,..., 8, 9`
- Avoid use of exclusive range as much as possible
```
(1..10).class
# Range

inclusive = 1..10
exclusive = 1..10

inclusive.begin
# 1

inclusive.first
# 1

inclusive.end
# 10

inclusive.last
# 10

exclusive.begin
# 1

exclusive.first
# 1

exclusive.end
# 10

exclusive.last
# 10

array = [*inclusive]
# Explodes the range out into an array
# [1, 2, 3,..., 9, 10]

array = [*exclusive]
# Explodes the range out into an array
# [1, 2, 3,..., 9], 10 is not included

alpha = 'a'..'g'
alpha.include?('g')
# true
```
# Constants
- Similar to variables
- Constant variable value should not change
- Ruby gives warning when const variable value is changed
- Variable names in uppercase, although having just the first letter in uppercase also works
```
MAX_SCORE = 100
max_score = 50

MAX_SCORE == max_score
# false
```
## Nil
- nil is an object
- nil.class => NilClass
- nil == false => false
- nil.nil? => true
```
product.nil?
# true

product == nil
# true

!product
# false
```
# Control Structures
## if, else and elsif
```
if boolean
  # ...
end

if fruit == 'apple'
  puts fruit.upcase
end

if boolean
  # ...
else
  # ...
end

if boolean
  # ...
elsif boolean
  # ...
else
  # ...
end
```
## unless
```
unless boolean
  # ...
end

# same as
if !boolean
  # ...
end

unless array.empty?
  # ...
end
```
## case
```
case
when boolean
  # ...
when boolean
  # ...
when boolean
  # ...
else
  # ...
end

case
when count == 0
  puts "nobody"
when count == 1
  puts "1 person"
when (2..5).include?(count)
  puts "several people"
else
  puts "many people"
end

case test_value
when value1
  # ...
when value2
  # ...
else
  # ...
end

case count
when 0
  puts "nobody"
when 1
  puts "1 person"
when 2..5
  puts "several people"
else
  puts "many people"
end
```
## Shorthand operators
```
# Ternary op
boolean ? result1 : result2

puts count == 1 ? "person" : "people"

# same as
if count == 1
  puts "person"
else
  puts "people"
end

# Or op
x = y || z

# same as
if y
  x =y
else
  x = z
end

# Or-Equals op
x ||=y

# same as
unless x
  x = y
end

# Statement modifiers
puts "Hello" if greeting_enabled
score += 10 unless score >= MAX_SCORE
```
# Loops
```
loop do
  # ...
end

i = 5
loop do
  break if i <= 0
  puts "Countdown: #{i}"
  i -= 1
end

while boolean
 # ...
end

until boolean
  # ...
end

i = 5
while i > 0
  puts "Countdown: #{i}"
  i -= 1
end
```
# Iterators
- Integer: times, upto, downto, step
- Range: each, step
- String: each_line, each_char, each_byte
- Array: each, each_index, each_with_index
- Hash: each, each_key, each_value, each_pair
```
i = 5

# times iterator
i.times do
  puts "Countdown: #{i}"
  i -= 1
end

# upto iterator
1.upto(5) {
  puts "Hello"
}

# downto(1) {
  puts "Hello"
}

(1..5).each {
  puts "Hello"
}

# Block variable
5.downto(1) do |i|
  puts "Countdown: #{i}"
end

fruits = ['banana', 'apple']
fruits.each do |fruit|
  puts fruit.capitalize
end

# for in loop, not recommended
for fruit in fruits
  puts fruit.capitalize
end
```
# Scripting
- Give ruby files a `.rb` extension
- Put a shebang line at the top - `#!/usr/bin/env ruby`
- Exit commands - `exit`, `exit!`, `abort(msg)`, type `control + c`
## Input and Output
### Output
- puts (adds line return)
- print (does not add line return)
```
puts "Hello"
print "Hello\n"
```
### Input
- gets - gets everything up until user hits enter and has line return in it
- chop - remove the last char of a string
- chomp - return last char of a string only if it is a newline
```
print "What is your name? " 
response = gets

puts "Hello, #{response}!"
# Hello, Billy
# !


print "What is your name? " 
response = gets.chomp

puts "Hello, #{response}!"
# Hello, Billy!
```
# Code Blocks
- Curly-brace format
  - Single line blocks
  - Blocks that return data without making any changes
- Do-end format
  - Multiline blocks
  - Blocks that perform actions, make changes
```
scores = {low: 2, high: 8, avg: 5}

scores.each do |k,v|
  puts "#{k.capitalize}: #{v}"
end

scores.each { |k,v| puts "#{k.capitalize}: #{v}" }
```
# Enumerables
- Countable items
- Arrays
- Ranges
- Hashes
- Strings (Makes sense for single byte characters only)
## Methods
- count
- each
- find
- map
- inject
- sort
- merge
- & many more
### Find Methods
- find / detect
- find_all / select
- any?, one?
- delete_if
```
(1..10).find { |n| n == 5 }
# 5

(1..10).detect { |n| n == 5 }
# 5

(1..10).detect { |n| n == 5 }
# 5

pantry = {'banana' => 10, 'apple' => 5}
pantry.find {|k, v| v == 5}
# ["apple", 5]


pantry.any? {|k, v| v == 5}
# true

pantry.none? {|k, v| v == 5}
# false

pantry.all? {|k, v| v == 5}
# false

pantry.one? {|k, v| v == 5}
# true

numbers = [*1..10]
numbers.delte_if {|n| n%2 == 1}
# [2, 4, 6, 8, 10]
```
### Map Methods
- map / collect
- Iterate through an enumerable, execute a code block on each item and add the result of the block to a new array
- Number of items in = Number of items out
```
x = [*1..5]

y = x.map {|n| n+1}
# [2, 3,..., 5]

x.map! {|n| n+1}
# Result same as above but here original array is modified (effect of exclamation mark)

z = x.collect {|n| n*50}
# [50, 100,..., 250]

pantry = {'banana' => 10, 'apple' => 5}

pantry.map {|k,v| "#{k.capitalize} : #{v}"}
# ["banana : 10", "apple : 5"]
```
### Inject Methods
- inject / reduce
- Accumulator
- Block variable to use for accumulation
- Optionally, takes default value as input
- Ruby convention: `memo` for block variable name
```
(1..5).inject {|memo, n| memo + n}
# 15

# Return values matter
(1..5).inject do |memo, n|
  memo + n
  x = 0 # Return value
end
# 0

fruits = ['apple', 'banana', 'pear']
total_size = fruits.inject(0) {|memo, fruit| memo + fruit.length}
# 15
```
### Sort Methods
- Uses comparison operator (<=>)
- Comp op returns -1 if value1 is less than value2, 0 if equal and 1 if greater
```
1 <=> 2
# -1

2 <=> 1
# 1

arr = [5, 8, 2, 6, 1, 3]

sarr = arr.sort {|v1,v2| v1 <=> v2}
# [1, 2, 3, 5, 6, 8]

sarr = arr.sort {|v1,v2| v2 <=> v1}
# [8, 6, 5, 3, 2, 1]

fruits = ['banana', 'apple', 'pear']

x = fruits.sort
# ['apple', 'banana', 'pear']

fruits.sort!
# ['apple', 'banana', 'pear']

x = fruits.sort do |fruit1, fruit2|
  fruit1.length <=> fruit2.length
end
# ['pear', 'apple', 'banana']

hash = {a: 4, c: 5, b: 3}

hash.sort {|p1, p2| p1[0] <=> p2[0]}
# [[:a, 4], [:b, 3], [:c, 5]]
```
### Merge Methods
- Used for hashes only
- Merges two hashes together
- Block can provide rules to use when merging
```
h1 = {a: 2, b: 4, c: 6}
h2 = {a: 3, b: 4, d: 8}

h1.merge(h2)
# {:a => 3, :b => 4, :c => 6, :d => 8}

h2.merge(h1)
# {:a => 2, :b => 4, :c => 6, :d => 8}

h1.merge(h2) {|key,old,new| new}
# {:a => 3, :b => 4, :c => 6, :d => 8}

h1.merge(h2) {|key,old,new| old}
# {:a => 2, :b => 4, :c => 6, :d => 8}
```
# Custom Methods
- Must be defined before they can be called
- Can be redefined without error
- Naming conventions
  - Lowercase with underscores
  - First char lowercase or underscore
  - Contains letters, digits, underscores
  - Last char can be ?!=
  - Avoid using same names for vars and methods
- Variable scope
  - Outside local variables are not accessible inside a method
  - Global, class and instance vars accessible inside a method
- Arguments
  - Order and number of args must match
  - Parenthesis are optional
  - Methods with args use them and vice versa, both when defining and calling methods
  - Arg can take default value and with default value it becomes optional arg
  - Required args listed first, optional args listed last
- Return Values
  - Methods return the last operation's value by default
  - `return`: return a value and exit the method
  - Methods can only return one value. Use array for returning multiple values with multiple assignments
```
def some_name
  # ...
end

def welcome
  puts "Hello world!"
end

welcome
# Hello world!

value = 10 # Local var

def output_value
  puts value
end

output_value
# undefined local variable or method for 'value'

def volume x, y, z
  x * y * z
end

volume 1, 2, 3
# 24

def welcome(greeting, name, punc='!')
  greeting + ' ' + name + punct
end

puts welcome('Hello', 'friend')
# Hello friend!

# Recommended way for multiple optional args
def welcome(greeting, options={}) {
  name = options[:name] || 'friend'
  punct = options[:punct] || '!
  greeting + ' ' + name + punct
end
}

puts welcome('Hello', {:punct => '!!!'})

def subtract(n1, n2)
  return n1 - n2
end

def add_and_subtract(n1, n2)
  add = n1 + n2
  sub = n1 - n2

  [add, sub]
end

# multiple assignment using comma-separated variables
a, s = add_and_subtract(8, 3)
```
