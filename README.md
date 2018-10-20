# Ruby-Ruby-Ruby-Ruby

## String

#### Puts

```rb
puts 'hello world' # hello world
```

#### String Interpolation

```rb
name = 'Sammy'
puts "Hello, my name is #{name}." # Hello, my name is Sammy.
```

#### Concatenation

```rb
str = 'foo'
str += 'bar'
puts str # foobar


str = 'hello'
str << 'world'
puts str # helloworld
```

#### Indexing & Slicing

Negative indexes are counted from the end (-1)

Slice by length using a comma (,): [startIndex, length]

Slice by index using (..): [startIndex..endIndex]

```rb
str = 'abcdefghijklmnop'

puts str[0] # a
puts str[0,5] # abcde
puts str[3, 5] # defgh

puts str[-1] # p
puts str[-7] # j
puts str[-7, 3] # jkl
```

```rb
str = 'hello world'

puts str[1..-1] # ello world

puts str[0..4] # hello
puts str[6..10] # world

puts str[-11..-7] # hello
puts str[-5..-1] # world
```

Use an exclamation mark to mutate the original object (bang method)

```rb
str = 'we deliver awesomeness'

subStr = str.slice(3, 4)
puts subStr # deli
puts str # we deliver awesomeness

puts str.slice!(11..17) # awesome
puts str # we deliver ness
```

#### Uppercase & Lowercase

```rb
str = 'let it never be said'
puts str.capitalize # Let it never be said

puts str.upcase # LET IT NEVER BE SAID

str = 'THE ROMANCE IS DEAD'
puts str.downcase # the romance is dead


# Using (!) to modify the original

str = 'are you serious bro?'
str.upcase!
puts str # ARE YOU SERIOUS BRO?
```

#### index & rindex

.index() returns the index of the **FIRST** occurrence of the given substring

```rb
str = 'hello'
puts str.index('e') # 1
puts str.index('lo') # 3
puts str.index('l') # 2
puts str.index('world') # nil
```

.rindex() returns the index of the **LAST** occurrence of the given

```rb
str = 'tomorrow is cancelled'
puts str.rindex('r') # 5
puts str.rindex('o') # 6
puts str.rindex('ed') # 19
```

#### reverse

```rb
str = 'foobar'
puts str.reverse # raboof
puts str # foobar

str = 'ruby on rails'
str.reverse!
puts str # sliar no ybur
```
