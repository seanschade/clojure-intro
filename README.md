[Recorded Presentation](http://www.youtube.com/watch?feature=player_embedded&v=3qLESFQK8ok)

# Getting Started With Clojure
* Install [Homebrew](url:http://mxcl.github.io/homebrew/)
	* `ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"`
* Install [Leiningen](https://github.com/technomancy/leiningen)
	* brew install leiningen
* Open the REPL (Read Eval Print Loop)
	* lein repl

### A Simple Function

	(+ 1 2)
	=> 3

### Operators are prefix versus infix

	(+ 1 2)
	(1 + 2)

### This makes arity simple when defining functions. + is a function. 

	(+ 1 2 3 4 5 6 7 8 9)
	=> 45
### Let's look at some other functions

	(+ 1 2 3 4 5 6 7 8 9)
	=> 45

	;; We can make this better
	(range 10)
	=> (0 1 2 3 4 5 6 7 8 9)
	(apply + (range 10))
	=> 45

	;; (doc fn) will provide the documentation for any function
	(doc range)
	------------------------
	clojure.core/range
	([] [end] [start end] [start end step])
	Returns a lazy seq of nums from start (inclusive) to end (exclusive), 
	by step, where start defaults to 0, 
	step to 1, and end to infinity.
	
	;; How would you create a list of all the even numbers from 0 to 100?
	(range 0 101 2)
	=>(0 2 4 6 8 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38 40 42 44 46 48 50 52 54 56 58 60 62 64 66 68 70 72 74 76  78 80 82 84 86 88 90 92 94 96 98 100)

	;; Several options available to solve the same problem
	(filter even? (range 101))
	=>(0 2 4 6 8 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38 40 42 44 46 48 50 52 54 56 58 60 62 64 66 68 70 72 74 76  78 80 82 84 86 88 90 92 94 96 98 100)

### Clojure Collections 

#### List

The List is the most common Clojure collection type and is represented by parentheses ()

The List has a special evaluation. The first item in the list is expected to be a function. To override this behavior prefix a list with a quote '()

	(def nums '(1 2 3 4 5))
	=> 'user/nums
	nums
	=> (1 2 3 4 5)
	(first nums)
	=> 1
	(last nums)
	=> 5 
	(rest nums)
	=> (2 3 4 5)
	(take 2 nums)
	=> (1 2)
	(map inc nums)
	=> (2 3 4 5 6)
	nums
	=> (1 2 3 4 5)
	;; nums didn't change because it is immutable!
	;; this is a good thing!
	;; 
	;; add items to a list using conj
	(conj '(1 2 3) 4)
	=> (4 1 2 3)
	;; items are added to the beginning of a List

#### Vector

A Vector is the second most common collection type and is represented by brackets []

	(def a-vec [1 2 3 4 5])
	=> 'user/a-vec
	a-vec
	=> [1 2 3 4 5]
	;; items are added to the end of a Vector
	(conj [1 2 3] 4)
	=> [1 2 3 4]
	;; use the vec function to create a Vector from a sequence
	(vec (range 10))
	=> [0 1 2 3 4 5 6 7 8 9]
	;; items in a Vector can be accessed by their index in constant time
	(nth [1 2 3 4] 1)
	=> 2
	(get [1 2 3 4] 1)
	=> 2
	([1 2 3 4] 1)
	=> 2
	;; vectors can be used as stacks
	(def a-stack [1 2 3])
	=> 'user/a-stack
	(peek a-stack)
	=> 3
	(pop a-stack)
	=> [1 2]
	;; pop returns a new vector with the last item removed
	;; the original stack is unchanged
	(conj a-stack 4)
	=> [1 2 3 4]
	a-stack
	=> [1 2 3]
	;; conj returns a new stack
	;; a-stack is unchanged

#### Map

A Map is a collection of key/value pairs and is represented by braces {}

	(def a-map {:a 1, :b 2, :c 3})
	=> 'user/a-map
	a-map
	=> {:a 1, :b 2, :c 3}
	;; use zipmap to create a map from 2 sequences
	(zipmap [:a :b :c] [1 2 3])
	=> {:c 3, :b 2, :a 1}

### Use lein new my-app to create a skeleton project

	lein new app my-app

## Have fun!
