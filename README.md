# Ruby-Ruby-Ruby-Ruby

## MADE WITH ♥ BY JAY

### Data Types in Ruby

1. Strings
2. Numbers
3. Booleans
4. Arrays
5. Hashes
6. Symbols

### type checking (.class)

```ruby
'hello'.class #=> String
'123.456'.class #=> String

987.class #=> Integer
3.14159.class #=> Float

true.class #=> TrueClass
false.class #=> FalseClass

[1, 2, 3, 4, 5].class #=> Array

{'name' => 'peter', 'age' => 69, :gender => 'male'}.class #=> Hash

:id.class #=> Symbol
:gender.class #=> Symbol
```

## String

### puts

```ruby
puts 'hello world' #=> hello world
puts 2 + 2 #=> 4
puts true || false #=> true
puts 321 > 123 #=> true
```

### string interpolation (preferred over concatenation)

Double quotation marks(" ") has to be used for string interpolation

```ruby
name = 'Sammy'
puts "Hello, my name is #{name}." #=> Hello, my name is Sammy.
puts "2 + 2 is #{2 + 2}" #=> 2 + 2 is 4

first_name = 'Peter'
last_name = 'Griffin'
full_name = "#{first_name} #{last_name}"

puts "Hello, I am #{full_name}." #=> Hello, I am Peter Griffin.
```

### concatenation

```ruby
str = 'foo'
str += 'bar'
str #=> foobar


str = 'hello'
str << ' world'
str #=> hello world

str = 'Mac'
str.concat('Book')
str #=> MacBook
```

### delete

```ruby
str = 'hello world'

# deletes all occurrences of each letter
sub_str = str.delete('lo')
sub_str #=> he wrd
str #=> hello world

# use (!) to delete from the original
str = 'hello world'
str.delete!('hed')
str #=> llo worl
```

### repetition

to repeat a string, use (string \* integer)

```ruby
str = 'hello'
repeated = str * 3
repeated #=> hellohellohello
```

### uppercase & lowercase (capitalize, upcase, downcase)

```ruby
str = 'let it never be said'
str.capitalize #=> Let it never be said

str = 'HELLO WORLD!'
str.capitalize #=> Hello world!
```

```ruby
str = 'let it never be said'
str.upcase #=> LET IT NEVER BE SAID

str = 'THE ROMANCE IS DEAD'
str.downcase #=> the romance is dead
```

Use a bang method (!) to modify the original

```ruby
str = 'are you serious bro?'
str.upcase!
str #=> ARE YOU SERIOUS BRO?
```

Bonus: swapcase

```ruby
str = 'This Is Weird'
str.swapcase!
str #=> tHIS iS wEIRD
```

### length

```ruby
str = 'hello world'
str.length #=> 11
```

### count

```ruby
str = 'hello world'
str.count('h') #=> 1
str.count('o') #=> 2
str.count('l') #=> 3

# counts by individual letters and returns the sum
str = 'hello world'
str.count('lo') #=> 5 (l => 3, o => 2)
str.count('eh') #=> 2 (e => 1, h => 1)
```

### string indexing & slicing

Negative indexes are counted from the end (-1)

Slice by length using a comma (,): [startIndex, length]

Slice by index using (..): [startIndex..endIndex]

```ruby
str = 'abcdefghijklmnop'

str[0] #=> a
str[0,5] #=> abcde
str[3, 5] #=> defgh

str[-1] #=> p
str[-7] #=> j
str[-7, 3] #=> jkl
```

```ruby
str = 'hello world'

str[1..-1] #=> ello world

str[0..4] #=> hello
str[6..10] #=> world

str[-11..-7] #=> hello
str[-5..-1] #=> world
```

Use an exclamation mark to mutate the original object (bang method)

```ruby
str = 'we deliver awesomeness'

sub_str = str.slice(3, 4)
sub_str #=> deli
str #=> we deliver awesomeness

str.slice!(11..17) #=> awesome
str #=> we deliver ness
```

### getting the index (index & rindex)

.index() returns the index of the **FIRST** occurrence of the given substring

```ruby
str = 'hello'
str.index('e') #=> 1
str.index('lo') #=> 3
str.index('l') #=> 2
str.index('world') #=> nil
```

.rindex() returns the index of the **LAST** occurrence of the given

```ruby
str = 'tomorrow is cancelled'
str.rindex('r') #=> 5
str.rindex('o') #=> 6
str.rindex('ed') #=> 19
```

### string reverse

```ruby
str = 'foobar'
str.reverse #=> raboof
str #=> foobar

str = 'ruby on rails'
str.reverse!
str #=> sliar no ybur
```

### substitution (sub & gsub)

.sub(pattern, replacement) for replacing the **FIRST** occurrence

```ruby
str = 'hello world'
str.sub('l', '') #=> helo world
str #=> hello world

str = 'exciting'
str.sub!('ing', 'ement') #=> excitement
str #=> excitement
```

.gsub(pattern, replacement) for replacing **ALL** occurrences

```ruby
str = 'are vowels important?'
str.gsub(/[aeiou]/, '') #=> r vwls mprtnt?
str #=> are vowels important?

str = 'wow nice one'
str.gsub!('o', '0')
str.gsub!('i', '1')
str.gsub!('e', '3')
str #=> w0w n1c3 0n3
```

### split

.split(pattern) splits on whitespace if no arguments are passed

```ruby
sentence = 'have a nice day'
words = sentence.split(' ')
# alternatives
# words = sentence.split
# words = sentence.split()

words #=> ["have", "a", "nice", "day"]
sentence #=> have a nice day



str = 'hello'
str_split = str.split('')
str_split #=> ["h", "e", "l", "l", "o"]
```

### strip

.strip removes whitespace from the start and end

```ruby
str = '   hello world!   '
str.length #=> 18
str.strip!
str #=> hello world!
str.length #=> 12
```

### type conversion (to_i, to_f)

.to_i => to integer

```ruby
str = '12345'
num = str.to_i
num #=> 12345 (integer)

# type checking using ===
Integer === num #=> true

# rounds down for values with decimal points
str = '123.456'
num = str.to_i
num #=> 123 (integer)

# alternative
str = '12345'
num = Integer(str)
num #=> 12345 (integer)
```

.to_f => to float

```ruby
str = '12345'
num = str.to_f
num #=> 12345.0 (float)

# type checking using ===
Float === num #=> true

# alternative
str = '123.456'
num = Float(str)
num #=> 123.456 (float)
```

## Number

### operators (+, -, \*, /, \*\*, %)

```ruby
2 + 2 #=> 4

10 - 3 #=> 7

4 * 2 #=> 8

10 / 2 #=> 5
9 / 2 #=> 4 (returns only integer)

9 / 2.to_f #=> 4.5 (either of the values has to be a float)
9.0 / 2 #=> 4.5
9 / 2.0 #=> 4.5

# exponent/power operator (**)
2 ** 3 #=> 8
3 ** 2 #=> 9
5 ** 2 #=> 25

# modulo operator (returns the remainder)
9 % 5 #=> 4
10 % 5 #=> 0
11 % 5 #=> 1
12 % 5 #=> 2

# use (% 2) for odd/even check
21 % 2 #=> 1 (odd)
10 % 2 #=> 0 (even)
33 % 2 #=> 1 (odd)
32 % 2 #=> 0 (even)
```

### odd, even (odd?, even?)

```ruby
21.odd? #=> true
10.even? #=> true

45.even? #=> false
12.odd? #=> false
```

### random

rand returns a random float between 0 and 1

```ruby
rand #=> 0.27471334647378365
```

rand(int) returns an random integer between 0 and int, not including int

```ruby
rand(10) #=> 6
rand(2) #=> either 1 or 0
rand(5) #=> either 0, 1, 2, 3, 4
```

### square root (Math.sqrt)

```ruby
Math.sqrt(25) #=> 5.0
Math.sqrt(24) #=> 4.898979485566356
```

## Array

### empty?

```ruby
arr = [1, 2, 3, 4, 5]
arr.empty? #=> false

other_arr = []
other_arr.empty? #=> true
```

### size of array (preferred)

```ruby
arr = ['a', 'b', 'c', 'd', 'e']
arr.size #=> 5

# alternatives
arr.length #=> 5
arr.count #=> 5
```

### clear

```ruby
arr = ['arrays', 'are', 'so', 'fun']
arr.clear
arr #=> []
arr.empty? #=> true
```

### range

```ruby
arr = (0..10).to_a
arr #=> [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

### fill

```ruby
arr = ['elements', 'in', 'an', 'array']
arr.fill('magic')
arr #=> ['magic', 'magic','magic', 'magic']

nil_arr = Array.new(5)
nil_arr #=> [nil, nil, nil, nil, nil]
nil_arr.fill('wow')
nil_arr #=> ['wow', 'wow', 'wow', 'wow', 'wow']
```

### compact

```ruby
arr = [1, 2, 3]
arr.length #=> 3
arr[5] = 'hello'
arr #=> [1, 2, 3, nil, nil, 'hello']
arr.length #=> 6

arr.compact!
arr #=> [1, 2, 3, 'hello']
```

### include?

```ruby
arr = ['a', 'b', 'c', 'd', 'e']
arr.include?('a') #=> true
arr.include?(10) #=> false
arr.include?('hello') #=> false
```

### join

```ruby
arr = ['a', 'b', 'c', 'd', 'e']
letters = arr.join
letters #=> abcde

arr = ['these', 'words', 'form', 'a', 'sentence']
sentence = arr.join(' ')
sentence #=> these words form a sentence
```

### min & max

```ruby
arr = [10, 8, 12, 9, 5, 11, 7, 6]
arr.min #=> 5
arr.max #=> 12
```

### index / rindex

.index(search_value) returns the index of the **FIRST** object for which block is true or nil if no match is found

```ruby
arr = ['a', 'b', 'c', 'd', 'e']
arr.index('c') #=> 2
arr.index('hello world') #=> nil
arr.index('e') #=> 4

arr.index('yes') == nil #=> true
```

.rindex(search_value) returns the index of the **LAST** object for which block is true or nil if no match is found

```ruby
arr = ['yes', 'no', 'maybe', 'no', 'yes']
arr.rindex('yes') #=> 4
arr.rindex('no') #=> 3
```

### first & last

```ruby
arr = ['alex', 'ben', 'charlie', 'david', 'ethan']
arr.first #=> alex
arr.first(2) #=> ['alex', 'ben']

arr = ['alex', 'ben', 'charlie', 'david', 'ethan']
arr.last #=> ethan
arr.last(3) #=> ['charlie', 'david', 'ethan']
```

### array indexing & slicing

Negative indexes are counted from the end (-1)

Slice by length using a comma (,): [startIndex, length]

Slice by index using (..): [startIndex..endIndex]

```ruby
arr = ['alex', 'ben', 'charlie', 'david', 'ethan']
arr[0] #=> alex
arr[-1] #=> ethan
arr[2] #=> charlie

arr[3, 2] #=> ['david', 'ethan']
arr[2, 1] #=> ['charlie']

arr[2..4] #=> ['charlie', 'david', 'ethan']
arr[0..2] #=> ['alex', 'ben', 'charlie']

arr[-3, 2] #=> ['charlie', 'david']
arr[-3..-1] #=> ['charlie', 'david', 'ethan']
```

```ruby
arr = ['hello', 'world', 'this', 'is', 'an', 'array']
sub_arr = arr.slice!(1, 4)
sub_arr #=> ['world', 'this', 'is', 'an']
arr #=> ['hello', 'array']

arr = ['alex', 'ben', 'charlie', 'david', 'ethan']
sub_arr = arr.slice!(2..3)
sub_arr #=> ['charlie', 'david']
arr #=> ['alex', 'ben', 'ethan']

arr = ['these', 'are', 'some', 'values', 'in', 'an', 'array']
sub_arr = arr.slice!(-4, 3)
sub_arr #=> ['values', 'in', 'an']
arr #=> ['these', 'are', 'some', 'array']

arr = ['I', 'am', 'getting', 'bored', 'of', 'ruby']
sub_arr = arr.slice!(-4..-2)
sub_arr #=> ['getting', 'bored', 'of']
arr #=> ['I', 'am', 'ruby']
```

### unique values (uniq)

```ruby
arr = [1, 1, 2, 2, 3, 3, 3, 4, 4, 5, 5, 6, 6]
arr.uniq!
arr #=> [1, 2, 3, 4, 5, 6]
```

### array reverse

```ruby
arr = ['hello', 'what', 'is', 'your', 'name']
arr.reverse!
arr #=> ['name', 'your', 'is', 'what', 'hello']
```

### shuffle

```ruby
arr = [1, 2, 3, 4, 5]
arr.shuffle!
arr #=> [3, 5, 2, 4, 1] (results will vary)
arr.shuffle!
arr #=> [4, 5, 1, 3, 2] (results will vary)
```

### concat

```ruby
first_arr = [1, 2, 3]
second_arr = [4, 5, 6]

first_arr.concat(second_arr)
first_arr #=> [1, 2, 3, 4, 5, 6]
second_arr #=> [4, 5, 6]

# alternative
first_arr = [1, 2, 3]
second_arr = [4, 5, 6]

first_arr += second_arr
first_arr #=> [1, 2, 3, 4, 5, 6]
second_arr #=> [4, 5, 6]
```

### push

Add an element/elements to the **END** of the array and return the array

```ruby
# using shovel operator (preferred)
arr = [1, 2, 3, 4, 5]
arr << 6 << 7
arr #=> [1, 2, 3, 4, 5, 6, 7]
arr << 'hello'
arr #=> [1, 2, 3, 4, 5, 6, 7, 'hello']

# alternative
arr = ['a', 'b', 'c', 'd', 'e']
arr.push('f')
arr #=> ['a', 'b', 'c', 'd', 'e', 'f']

arr.push('g', 'h')
arr #=> ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h']
```

### pop

Remove an element from the **END** of the array and return the element

```ruby
arr = ['this', 'is', 'the', 'last', 'item']
arr.pop #=> item
arr #=> ['this', 'is', 'the', 'last']
```

.pop(int) will remove int number of elements from the **END** of the array and return an array of the elements

```ruby
arr = ['a', 'b', 'c', 'd', 'e']
arr.pop(2) #=> ['d', 'e']
arr #=> ['a', 'b', 'c']
```

### unshift

Add an element/elements to the **START** of the array and return the array

```ruby
arr = ['c', 'd', 'e']
arr.unshift('a', 'b')
arr #=> ['a', 'b', 'c', 'd', 'e']

arr.unshift('what')
arr #=> ['what', 'a', 'b', 'c', 'd', 'e']
```

### shift

Remove an element from the **START** of the array and return the element

```ruby
arr = ['first', 'second', 'third', 'fourth']
arr.shift #=> first
arr #=> ['second', 'third', 'fourth']
```

.shift(int) will remove int number of elements from the **START** of the array and return an array of the elements

```ruby
arr = ['first', 'second', 'third', 'fourth']
arr.shift(3) #=> ['first', 'second', 'third']
arr #=> ['fourth']
```

### insert(index, val...)

```ruby
arr = ['when', 'I', 'was', 'a', 'young', 'boy']
arr.insert(-3, 'stupid')
arr #=> ['when', 'I', 'was', 'a', 'stupid', 'young', 'boy']

arr = ['my', 'father', 'took', 'me', 'into', 'the', 'city']
arr.insert(2, 'what', 'is', 'this')
arr #=> ['my', 'father', 'what', 'is', 'this', 'took', 'me', 'into', 'the', 'city']
```

### delete(val)

```ruby
arr = ['a', 'b', 'c', 'd', 'e', 'f']
arr.delete('c')
arr #=> ['a', 'b', 'd', 'e', 'f']
```

### delete_at(index)

```ruby
arr = ['this', 'is', 'a', 'CAT MEOWS', 'strange', 'sentence']
arr.delete_at(3)
arr #=> ['this', 'is', 'a', 'strange', 'sentence']
```

### delete_if{ |item| condition }

```ruby
scores = [50, 20, 33, 70, 83, 89, 48, 100]
scores.delete_if {|i| i < 50}
scores #=> [50, 70, 83, 89, 100]
```

### sort

```ruby
arr = ['d', 'a', 'e', 'c', 'b']
arr.sort!
arr #=> ['a', 'b', 'c', 'd', 'e']

arr = [20, 10, 50, 30, 100, 1, 40]
arr.sort!
arr #=> [1, 10, 20, 30, 40, 50, 100]
```

use sort { |a, b| comparison } for implementing a comparison between a and b

```ruby
arr = ['d', 'a', 'e', 'c', 'b']
arr.sort! { |a, b| b <=> a }
arr #=> ['e', 'd', 'c', 'b', 'a']

arr = ['alex', 'ben', 'charlie', 'david', 'ethan']

arr.sort! { |a, b| a.length <=> b.length }
arr #=> ['ben', 'alex', 'david', 'ethan', 'charlie']

arr.sort! { |a, b| b.length <=> a.length }
arr #=> ['charlie', 'david', 'ethan', 'alex', 'ben']
```

### sum

```ruby
arr = [1, 2, 3, 4, 5]
arr.sum #=> 15

# use .sum(initial value) for specifying an initial value
arr = [10, 10, 10]
arr.sum(5) #=> 35
```

### each { |item| code block }

```ruby
str = ''
arr = [1, 2, 3, 4]

arr.each { |x| str << (x * 2).to_s }
str #=> '2468'
```

### each_index { |index| code block }

```ruby
arr = ['a', 'b', 'c', 'd', 'e']
arr.each_index { |x| puts "Index #{x} is #{arr[x]}" }

# Index 0 is a
# Index 1 is b
# Index 2 is c
# Index 3 is d
# Index 4 is e
```

### map { |item| code block }

```ruby
arr = [1, 2, 3, 4, 5]
new_arr = arr.map { |x| x * 2 }
new_arr #=> [2, 4, 6, 8, 10]

arr = ['a', 'b', 'c', 'd', 'e']
arr.map! { |x| "hi#{x}" }
arr #=> ['hia', 'hib', 'hic', 'hid', 'hie']

arr = [1, 2, 3, 4, 5]
other_arr = arr.map.with_index { |x, i| x + i }
other_arr #=> [1, 3, 5, 7, 9]
```

### select { |item| condition }

```ruby
arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
even_arr = arr.select { |x| x.even? }
even_arr #=> [2, 4, 6, 8, 10]

arr = ['here', 'are', 'some', 'words', 'that', 'are', 'inside', 'an', 'array']
arr.select! { |x| x.length >= 5 }
arr #=> ['words', 'inside', 'array']
```

### reduce { |sum, current| code block }

```ruby
arr = [1, 2, 3, 4, 5]
sum = arr.reduce { |acc, cur| acc + cur }
sum #=> 15

arr = [1, 2, 3, 4, 5]
sum = arr.reduce(:+)
sum #=> 15

arr = [10, 20, 30]
total_plus_seven = arr.reduce(7) { |acc, cur| acc + cur }
total_plus_seven #=> 67
```
