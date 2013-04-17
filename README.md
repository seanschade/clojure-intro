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

### Data Structures - List

The List is the most common Clojure data structure and is represented by parentheses ()

The List has a special evaluation. The first item in the list is expected to be a function. To override this behavior prefix a list with a quote '()

## Have fun!
