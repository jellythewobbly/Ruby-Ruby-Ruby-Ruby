# Ruby-Ruby-Ruby-Ruby

## String

### puts

```rb
puts 'hello world' #=> hello world
puts 2 + 2 #=> 4
puts true || false #=> true
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
puts str #=> foobar


str = 'hello'
str << ' world'
puts str #=> hello world

str = 'Mac'
str.concat('Book')
puts str #=> MacBook
```

### delete

```rb
str = 'hello world'

# deletes all occurrences of each letter
sub_str = str.delete('lo')
puts sub_str #=> he wrd
puts str #=> hello world

# use (!) to delete from the original
str = 'hello world'
str.delete!('hed')
puts str #=> llo worl
```

### repetition

to repeat a string, use (string \* integer)

```rb
str = 'hello'
repeated = str * 3
puts repeated #=> hellohellohello
```

### uppercase & lowercase (capitalize, upcase, downcase)

```rb
str = 'let it never be said'
puts str.capitalize #=> Let it never be said

str = 'HELLO WORLD!'
puts str.capitalize #=> Hello world!
```

```rb
str = 'let it never be said'
puts str.upcase #=> LET IT NEVER BE SAID

str = 'THE ROMANCE IS DEAD'
puts str.downcase #=> the romance is dead
```

Use a bang method (!) to modify the original

```rb
str = 'are you serious bro?'
str.upcase!
puts str #=> ARE YOU SERIOUS BRO?
```

Bonus: swapcase

```rb
str = 'This Is Weird'
str.swapcase!
puts str #=> tHIS iS wEIRD
```

### length

```rb
str = 'hello world'
puts str.length #=> 11
```

### count

```rb
str = 'hello world'
puts str.count('h') #=> 1
puts str.count('o') #=> 2
puts str.count('l') #=> 3

# counts by individual letters and returns the sum
str = 'hello world'
puts str.count('lo') #=> 5 (l => 3, o => 2)
puts str.count('eh') #=> 2 (e => 1, h => 1)
```

### indexing & slicing

Negative indexes are counted from the end (-1)

Slice by length using a comma (,): [startIndex, length]

Slice by index using (..): [startIndex..endIndex]

```rb
str = 'abcdefghijklmnop'

puts str[0] #=> a
puts str[0,5] #=> abcde
puts str[3, 5] #=> defgh

puts str[-1] #=> p
puts str[-7] #=> j
puts str[-7, 3] #=> jkl
```

```rb
str = 'hello world'

puts str[1..-1] #=> ello world

puts str[0..4] #=> hello
puts str[6..10] #=> world

puts str[-11..-7] #=> hello
puts str[-5..-1] #=> world
```

Use an exclamation mark to mutate the original object (bang method)

```rb
str = 'we deliver awesomeness'

sub_str = str.slice(3, 4)
puts sub_str #=> deli
puts str #=> we deliver awesomeness

puts str.slice!(11..17) #=> awesome
puts str #=> we deliver ness
```

### getting the index (index & rindex)

.index() returns the index of the **FIRST** occurrence of the given substring

```rb
str = 'hello'
puts str.index('e') #=> 1
puts str.index('lo') #=> 3
puts str.index('l') #=> 2
puts str.index('world') #=> nil
```

.rindex() returns the index of the **LAST** occurrence of the given

```rb
str = 'tomorrow is cancelled'
puts str.rindex('r') #=> 5
puts str.rindex('o') #=> 6
puts str.rindex('ed') #=> 19
```

### reverse

```rb
str = 'foobar'
puts str.reverse #=> raboof
puts str #=> foobar

str = 'ruby on rails'
str.reverse!
puts str #=> sliar no ybur
```

### substitution (sub & gsub)

.sub(pattern, replacement) for replacing the **first** occurrence

```rb
str = 'hello world'
puts str.sub('l', '') #=> helo world
puts str #=> hello world

str = 'exciting'
puts str.sub!('ing', 'ement') #=> excitement
puts str #=> excitement
```

.gsub(pattern, replacement) for replacing **all** occurrences

```rb
str = 'are vowels important?'
puts str.gsub(/[aeiou]/, '') #=> r vwls mprtnt?
puts str #=> are vowels important?

str = 'wow nice one'
str.gsub!('o', '0')
str.gsub!('i', '1')
str.gsub!('e', '3')
puts str #=> w0w n1c3 0n3
```

### split

.split(pattern) splits on whitespace if no arguments are passed

```rb
sentence = 'have a nice day'
words = sentence.split(' ')
# alternatives:
# words = sentence.split
# words = sentence.split()

puts words #=> ["have", "a", "nice", "day"]
puts sentence #=> have a nice day



str = 'hello'
str_split = str.split('')
puts str_split #=> ["h", "e", "l", "l", "o"]
```

### strip

.strip removes whitespace from the start and end

```rb
str = '   hello world!   '
puts str.length #=> 18
str.strip!
puts str #=> hello world!
puts str.length #=> 12
```

### type conversion (to_i, to_f)

.to_i => to integer

```rb
str = '12345'
num = str.to_i
puts num #=> 12345 (integer)

# type checking using ===
puts Integer === num #=> true

# rounds down for values with decimal points
str = '123.456'
num = str.to_i
puts num #=> 123 (integer)

# alternative:
str = '12345'
num = Integer(str)
puts num #=> 12345 (integer)
```

.to_f => to float

```rb
str = '12345'
num = str.to_f
puts num #=> 12345.0 (float)

# type checking using ===
puts Float === num #=> true

# alternative:
str = '123.456'
num = Float(str)
puts num #=> 123.456 (float)
```
