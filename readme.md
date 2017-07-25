Parser combinators implemented with Frank programming language, based on [frankjnr](https://github.com/cmcl/frankjnr) implementation.

## Project Overview

There are three interesting things here: two prototypes of parser combinators
libraries and one parser of minimal Markdown-like language.

### Parser as a combination of state and exceptions

The first library treats parser as a combination of two effects: state of the input
stream and exceptions. Source code can be found in file `src/Parser/Combination/Parser.fk` file.
There is also a proof of concept parser of extremely simplified Markdown implemented
on top of this library (look into `src/Parser/Combination/MDparser.fk`).

### Parser as a monolithic effect

Parser may be represented as a monolithic effect interface allowing to assign
several different interpretations to parsers with different effect handlers.

File `src/Parser/Monolithic/Parser.fk` has a simple example of such an effect for
parsing. 

## Running something

As far as Frank doesn't have module system of any kind, you may ask your `cat` to grab some files and concatenate them for you.

Take a look at the `run-examples.sh` file, something like that you should do to
run anything with Frank. Keep in mind that there must be at least one newline
character between every two files you would like to concatenate.

Files in the directory `src/base` are a collection of standard functional programming
primitives. 