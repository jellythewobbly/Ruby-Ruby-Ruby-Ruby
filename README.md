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

```rb
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

```rb
puts 'hello world' #=> hello world
puts 2 + 2 #=> 4
puts true || false #=> true
puts 321 > 123 #=> true
```

### string interpolation (preferred over concatenation)

Double quotation marks(" ") has to be used for string interpolation

```rb
name = 'Sammy'
puts "Hello, my name is #{name}." #=> Hello, my name is Sammy.
puts "2 + 2 is #{2 + 2}" #=> 2 + 2 is 4

first_name = 'Peter'
last_name = 'Griffin'
full_name = "#{first_name} #{last_name}"

puts "Hello, I am #{full_name}." #=> Hello, I am Peter Griffin.
```

### concatenation

```rb
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

```rb
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

```rb
str = 'hello'
repeated = str * 3
repeated #=> hellohellohello
```

### uppercase & lowercase (capitalize, upcase, downcase)

```rb
str = 'let it never be said'
str.capitalize #=> Let it never be said

str = 'HELLO WORLD!'
str.capitalize #=> Hello world!
```

```rb
str = 'let it never be said'
str.upcase #=> LET IT NEVER BE SAID

str = 'THE ROMANCE IS DEAD'
str.downcase #=> the romance is dead
```

Use a bang method (!) to modify the original

```rb
str = 'are you serious bro?'
str.upcase!
str #=> ARE YOU SERIOUS BRO?
```

Bonus: swapcase

```rb
str = 'This Is Weird'
str.swapcase!
str #=> tHIS iS wEIRD
```

### length

```rb
str = 'hello world'
str.length #=> 11
```

### count

```rb
str = 'hello world'
str.count('h') #=> 1
str.count('o') #=> 2
str.count('l') #=> 3

# counts by individual letters and returns the sum
str = 'hello world'
str.count('lo') #=> 5 (l => 3, o => 2)
str.count('eh') #=> 2 (e => 1, h => 1)
```

### indexing & slicing

Negative indexes are counted from the end (-1)

Slice by length using a comma (,): [startIndex, length]

Slice by index using (..): [startIndex..endIndex]

```rb
str = 'abcdefghijklmnop'

str[0] #=> a
str[0,5] #=> abcde
str[3, 5] #=> defgh

str[-1] #=> p
str[-7] #=> j
str[-7, 3] #=> jkl
```

```rb
str = 'hello world'

str[1..-1] #=> ello world

str[0..4] #=> hello
str[6..10] #=> world

str[-11..-7] #=> hello
str[-5..-1] #=> world
```

Use an exclamation mark to mutate the original object (bang method)

```rb
str = 'we deliver awesomeness'

sub_str = str.slice(3, 4)
sub_str #=> deli
str #=> we deliver awesomeness

str.slice!(11..17) #=> awesome
str #=> we deliver ness
```

### getting the index (index & rindex)

.index() returns the index of the **FIRST** occurrence of the given substring

```rb
str = 'hello'
str.index('e') #=> 1
str.index('lo') #=> 3
str.index('l') #=> 2
str.index('world') #=> nil
```

.rindex() returns the index of the **LAST** occurrence of the given

```rb
str = 'tomorrow is cancelled'
str.rindex('r') #=> 5
str.rindex('o') #=> 6
str.rindex('ed') #=> 19
```

### reverse

```rb
str = 'foobar'
str.reverse #=> raboof
str #=> foobar

str = 'ruby on rails'
str.reverse!
str #=> sliar no ybur
```

### substitution (sub & gsub)

.sub(pattern, replacement) for replacing the **FIRST** occurrence

```rb
str = 'hello world'
str.sub('l', '') #=> helo world
str #=> hello world

str = 'exciting'
str.sub!('ing', 'ement') #=> excitement
str #=> excitement
```

.gsub(pattern, replacement) for replacing **ALL** occurrences

```rb
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

```rb
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

```rb
str = '   hello world!   '
str.length #=> 18
str.strip!
str #=> hello world!
str.length #=> 12
```

### type conversion (to_i, to_f)

.to_i => to integer

```rb
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

```rb
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

```rb
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

```rb
21.odd? #=> true
10.even? #=> true

45.even? #=> false
12.odd? #=> false
```

### random

rand returns a random float between 0 and 1

```rb
rand #=> 0.27471334647378365
```

rand(int) returns an random integer between 0 and int, not including int

```rb
rand(10) #=> 6
rand(2) #=> either 1 or 0
rand(5) #=> either 0, 1, 2, 3, 4
```

### square root (Math.sqrt)

```rb
Math.sqrt(25) #=> 5.0
Math.sqrt(24) #=> 4.898979485566356
```

## Array

### empty?

```rb
arr = [1, 2, 3, 4, 5]
arr.empty? #=> false

other_arr = []
other_arr.empty? #=> true
```

### size of array (preferred method)

```rb
arr = ['a', 'b', 'c', 'd', 'e']
arr.size #=> 5

# alternatives
arr.length #=> 5
arr.count #=> 5
```

### include?

```rb
arr = ['a', 'b', 'c', 'd', 'e']
arr.include?('a') #=> true
arr.include?(10) #=> false
arr.include?('hello') #=> false
```

### index / rindex

.index(search_value) returns the index of the **FIRST** object for which block is true or nil if no match is found

```rb
arr = ['a', 'b', 'c', 'd', 'e']
arr.index('c') #=> 2
arr.index('hello world') #=> nil
arr.index('e') #=> 4
```

.rindex(search_value) returns the index of the **LAST** object for which block is true or nil if no match is found

```rb
arr = ['yes', 'no', 'maybe', 'no', 'yes']
arr.rindex('yes') #=> 4
arr.rindex('no') #=> 3
```

### unique values (uniq)

```rb
arr = [1, 1, 2, 2, 3, 3, 3, 4, 4, 5, 5, 6, 6]
arr.uniq!
arr #=> [1, 2, 3, 4, 5, 6]
```

### reverse

```rb
arr = ['hello', 'what', 'is', 'your', 'name']
arr.reverse!
arr #=> ['name', 'your', 'is', 'what', 'hello'
```

### push

```rb
arr = ['a', 'b', 'c', 'd', 'e']
arr.push('f')
arr #=> ['a', 'b', 'c', 'd', 'e', 'f']

arr.push('g', 'h')
arr #=> ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h']

# using shovel operator
arr = [1, 2, 3, 4, 5]
arr << 6
arr << 7
arr #=> [1, 2, 3, 4, 5, 6, 7]
```

### pop

```rb
arr = ['this', 'is', 'the', 'last', 'item']
arr.pop #=> item
arr #=> ['this', 'is', 'the', 'last']
```
