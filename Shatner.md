# Shatner: An Impractilang

Shatner is a highly impractical programming language which is best described as "idiotic programming by example".

A Shatner program has two parts:

* A collection of training inputs and outputs
* The main inputs

An example source file for Shatner:

    1,10
    10,100
    11,110
    1000
    1100

Each line containing a comma is a pair of training inputs: a binary input followed by a binary output. These are example transformations from input to output for an algorithm that Shatner will try to derive.

The lines without a comma are inputs that Shatner will run through its derived algorithm (should it ever find one that passes all the input/output examples).

## Implementing Shatner

For every integer N from 0 upwards:
Convert to base 8. Interpret this base 8 number as a string of Brainfuck commands, as follows:

    >   0
    <   1
    +   2
    -   3
    .   4
    ,   5
    [   6
    ]   7

Execute this Brainfuck program using all the training inputs in turn. If any training input does not produce the corresponding expected training output, move onto the next integer. If the Brainfuck program doesn't exit after 60 seconds on any input, stop executing it and consider the training input as failed.

If all the training inputs produce the expected training outputs for an integer N, run the found algorithm on the main inputs.

## Comments

Note that impractilangs are not necessarily Turing Complete.

Author: alex.hunsley@gmail.com
