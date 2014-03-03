# Regular Expresions: "Regex"

## Student Learning Objectives:
* <h2> By the end of this lesson you should be able to write regular expressions to:</h2>
	* <h3> test a string to see whether it matches a pattern.</h3>
	* <h3> extract from a string the sections that match all or part of a pattern.</h3>
	* <h3> change the string, replacing parts that match a pattern.</h3>
	
## Why learn Regular Expressions:
* <h3> Regular Expressions are a part of many programming languages: Ruby, JS, Perl, Python, Java, unix shell scripts (grep) ...
* <h3> Regular Expressions are used for pattern matching, find and replace tasks.
* <h3> Good for model validations: valid email format, valid phone format, valid ssn ...
* <h3> Regex is real cryptic code. You have to decipher it to understand it.

## 1) Match a pattern in a string

* <h3> The strategy is to not only match what you want, but don't match what you don't want.
* <h3> Each character in a regex is either a metacharacter with special meaning, or a regular character with its literal meaning.
* <h3> Exact pattern matches
	* <h3> Place exact string between to forward slashes: /cat/ matches "cat"
	* <h3> However, /cat/ also matches "catastrophe" and "scat" 
* <h3> Use metacharacters to be more specific on what you match.
	
###Matchers: .match and =~
* <h3> .match(/regex matcher/, "replacement string")
* <h3> "I love my cat.".match(/cat/)
* <h3> match[0] => cat
* <h3> "=~" # returns the index location in the string of the first match, can be used in true/false testing because no match return nil (remember in Ruby nil is false).
	* <h3> /cat/ =~ "cat"      # => 0
	* <h3> /bearcat/ =~ "cat"  # => 4
	* <h3> /cat/ =~ "Cat" # => nil

### Metacharacters:
* <h3> . - wild card, matches any char
* <h3> \ - escape a character, turns a metacharacter into a string literal - to match a literal period use \\.
* <h3> | - logical or, /cat|dog/ matches "cat" or "dog"
* <h3> \s - matches any whitespace
* <h3> \S - matches any non-whitespace
* <h3> ^ - start of line
* <h3> $ - end of line
* <h3> /cAt/i - "/i" case insensitive, matches Cat, cAt, CAT, CaT, cat ...

### Whiteboard:
* <h3> Type this sentence into Rubular (http://www.rubular.com/) and follow along.
* <h3> Dogs are not dogmatic about dog things unlike Madog the bad dog.

### Exercise 1:
* <h3> open "match_string.rb" in sublime, and follow the instructions within 
* <h3> run using: $ruby match_string.rb string_data

## 2) Select section out of a string

### Metacharacters:
* <h3> (...) - enclosed matches are assigned variable names $1+ that can be reused
* <h3> [] - range of characters or numbers to match: [0-9] or [a-z]
* <h3> \d - any digit, same as [0-9]
* <h3> \D - any non-digit
* <h3> {} - exact number of times character or number is repeated, a{2} == "aa"
* <h3> + - one or more
* <h3> * - zero or more
* <h3> ? - zero or one

### Whiteboard:
* <h3> Type this into Rubular (http://www.rubular.com/) and follow along.
* <h3> 2014-03-01
* <h3> see file: data_decomp.rb

### Exercise 2:
* <h3> open "real_time_data.rb" in sublime, and follow the instructions within 
* <h3> run using: $ruby read_time_data.rb time_data

## 3) Find and replace parts of a string

* <h3> Commands: .sub and .gsub
* <h3> .sub substitutes on first match, .gsub substitutes globally all matches
* <h3> Syntax: my_string.sub( /sub string to match/ , "replacement sub string" )
* <h3> "That is a cute dog.".sub(/dog/, "cat") => "That is a cute cat."
* <h3> Can be chained together:
	* <h3> "Red is my favorite color, I just love red".sub(/red/, "blue").sub(/Red/,"Blue")

### Exercise 3:
* <h3> open "find_replace.rb" in sublime, and follow the instructions within 
* <h3> run using: $ruby find_replace.rb find_replace_data

##@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
## Resources
### Rubular: regular expression tester: http://www.rubular.com/

