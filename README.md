# Start here

## First Bite

So Studies show that reading code and have small specific guided steps is 
the best way to learn. I think it also helps to skirt the truth tell necessary.

So that's what this guide is.

Lets look at some clojure

```clojure
(inc 1)
```

the output of that is `2`. you can read it as increment 1, which is 2.

Here is some more code...

```clojure
(+ 2 1)
```

the output is 3.

What if we wanted to define our own `inc` function?


```clojure
(defn our-inc [x] (+ 1 x))
```

read 
- `defn`    : define function
- `our-inc`: called our-inc
- `[x]`     : that takes one parameter `x`
- `+ 1 x`   : add 1 to x


the output of calling `our-inc` with 2 would be 3. just like increment.


the code is `+ 1 x` because clojure always puts the function first.

that means that in the code we have already seen:


```clojure
(inc 1)
(+ 2 1)
(defn our-inc [x] (+ 1 x))
```

inc, + and defn are all functions.

This is a rule of clojure *Functions come first!*
First in what? Its the first thing inside the parens.
Don't worry about the parens just yet. 

Congrats you just took your first bite of clojure!
Think about it a bit, no need to share.

## Second Bite

In our first bite, we learned:

* how to read some clojure code
* how to make a function
* that the first thing in the parens is a function

were not going to build on that right away. Instead were going to look at 
some other elements of clojure.

Clojure, like ruby, gives you some ways to organize information as part of the syntax.
like in ruby you can do:

```ruby
[1, 100, 7]
```

you can do that in clojure to:

```clojure
[1, 100, 7]
```

That's just putting numbers in an array. You can access things in Vectors by there position in the array.
Like "give me the item in position 1". and it would be 100. Because the first positions index is 0 for some weird 
quirk of history.

so for the example above
Pos value
0   1
1   100
2   7


Ruby and Clojure both also give you ways to describe hash maps. 

The ruby code

```ruby
{ "Jane Doe" => 10, 
  "Jim Doe" => 6 }
```

The clojure is a bit different basically we dont have the `=>` to separate the key and the value. you can read this as
every key needs a value. Its best to indent so each key value gets its own line because its easier to read. 

```clojure
{ "Jane Doe" 10, 
  "Jim Doe" 6 }
```


Where we could look things up via position
with vectors, you use the keys to look up items with hashmaps. So we could say "give me the value for Jane Doe" and it would be 10

Congrats! Thats your second bite.
The big idea here is that Clojure easily lets you organize your information into hash maps and vectors so you can 
easily access that information later. We call vectors and hashmaps datastructures. So you could say you learned
some datastructures if you wanted to sound fancy. We can also call them _collections_ because you _collect_ things in them.
 

Other languages make you type a lot more for the same thing. 
Dont try to read this, just notice that its a lot of lines!

```Java
import java.util.HashMap

  HashMap<String, Integer> map 
            = new HashMap<>(); 
  
        print(map); 
        map.put("vishal", 10); 
        map.put("sachin", 30); 
        map.put("vaibhav", 20); 
```

## Third Bite

Great job so far.

- In the first bite we learned how to define functions using `defn` and that the first thing in the paren is a function.
- In the second bite we learned about some ways to organize information into vectors and hashmaps which are both collections.

So we have collections, but there not very useful unless we can put and take things into them.

We have one way to put things in them already. When we type

```
[1, 100, 7]
```

we put 1 100 and 7 in the vector manually. But as we start to write programs will need to 
have a way to add things to our collections that isn't manually.

The way to add something to a vector is just like this:

```clojure
(conj [1, 100, 7] 8)
```

which would output `[1, 100, 7, 8]`

we can read this as

- `conj`          : conjoin 
- `[1, 100, 7]` : the collection
- `8`              : with 8

conjoin sounds weird, so if you like just think of it as append right now.

Lets look at adding something to the hashmap.

```clojure
(assoc {"first-name" "drew"} "last-name" "verlee")
```

the output of this is:

```clojure
{"first-name" "drew"
 "last-name" "verlee"}
```

you can read this as 

- `assoc`                           : associate
- `{"first-name" "last-name"}` : the collection
- `"last-name" "verlee"`        : with the new key and value



Super! You can now add some stuff to collections.
This is great, putting stuff in collections is a huge part of programming.

## Fourth Bite

lets quickly recap some of the bites.

- `defn` makes functions
- `[]` makes  a vector and `conj` adds things to it.
- `{}` make a hashmap and `assoc` adds things to it.

This bite were going to learn to take stuff out of collections.

Lets get somethings out of the vector.

```clojure
(nth [1, 100, 7] 0)
```

this returns `1`. 

you can read it as:

- `nth` give me the nth item
- `[1, 100, 7]` : from this collection
- `0`                  : here is that nth number 

ok, that one is a bit awkward. But notice that in all our examples so far the collection 
is the second item inside the parens. This is sort of nice.

```clojure
(conj [1, 100, 7] 8)
(nth [1, 100, 7] 0)
(assoc {"first-name" "drew"} "last-name" "verlee")
```

it looks like this pattern is...

`function collection items-to-add-to-the-collection`

this holds true for accessing things from hashmaps too.


```clojure
(get {"first-name" "drew"} "first-name")
```

this predicable outputs `drew`. 


Awesome!!! 

You might be tempted to feel like these bites are too small. Or that this isn't really
important. After all real programmers are super hardcore things. They aren't 
comfortable dealing with small bites. This isn't true. Defining collections
and putting things into them and getting stuff out of them is more then half of programming and its most of clojure.
All the other stuff, is mostly ceremony that _helps_ with that.


## Fifth Bite
