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
	Returns a lazy seq of nums from start (inclusive) to end (exclusive), by step, where start defaults to 0, step to 1, and end to infinity.
    
### Data Structures - List

The List is the most common Clojure data structure and is represented by parentheses ()

The List has a special evaluation. The first item in the list is expected to be a function. To override this behavior prefix a list with a quote '()

## Have fun!
