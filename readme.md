Experimental parsers combinators library(s) implemented with Frank programming language, based on [frankjnr](https://github.com/cmcl/frankjnr) implementation.

## Project Overview

There are three interesting things here: two prototypes of parser combinators
libraries and one parser of minimal Markdown-like language.

### Parser as a combination of state and exceptions

The first library treats parser as a combination of two effects: state of the input
stream and exceptions. Source code can be found in `src/ParserCombo/Parser.fk` file.
There is also a proof of concept parser of extremely simplified Markdown implemented
on top of this library (look into `src/ParserCombo/MDparser.fk`).

### Parser as a monolithic effect

In directory `src/ParserMonolith/` you can take a look at my attempts to implement
a monolithic parser effect in Frank. Unfortunately, I've run into limitations that
are discussed in section 9 'Future Work','' Dynamic Effects' paragraph of latest
(POPL'17) publication of Frank: there is no possibility to have existential types
in effects signatures.

## Running something

As far as Frank doesn't have module system of any kind, you may ask your `cat` to grab some files and concatenate them for you.

Take a look at the `run-examples.sh` file, something like that you should do to
run anything with Frank. Take in mind that there must be at least one newline
character between every two files you would like to cat.
