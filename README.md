# Getting Started With Clojure
* Install [Homebrew](url:http://mxcl.github.io/homebrew/)
	* `ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"`
* Install [Leiningen](https://github.com/technomancy/leiningen)
	* brew install leiningen
* Open Terminal
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

    

### Data Structures - List

The List is the most common Clojure data structure and is represented by parentheses ()

The List has a special evaluation. The first item in the list is expected to be a function. To override this behavior prefix a list with a quote '()

	(def nums '(1 2 3 4 5))
	=> 'user/nums
	nums
	(1 2 3 4 5)
	(first nums)
	=> 1
	(last nums)
	=> 5 
	(rest nums)
	=> (2 3 4 5)
	(map inc nums)
	=> (2 3 4 5 6)
	nums
	(1 2 3 4 5)
	;; nums didn't change because it is immutable!
	;; this is a good thing!


## Have fun!
