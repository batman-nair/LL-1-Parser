# LL(1) Parser

An LL(1) parser made in C++ with STL libraries.

It prints out the first, follow, parse table and checks if the given input string is accepted by the given grammar.


## Usage
Compile the code with g++ and run with arguments <grammar-file> <input-string>

Grammar file contains all the productions for the grammar.

* Each line contains a production for the grammar in the format LHS->RHS
* All upper case alphabets are non-terminals or variables.
* The letter e is considered as empty string or epsilon.
* Dollar sign is used as end character.
* Any other character is taken as a terminal for the grammar

Sample Usage: 

```bash
g++ parser.c -o parser
./parser grammar1.txt ab
```

Output:
```text
Grammar parsed from grammar file: 
0.  S -> AB
1.  A -> a
2.  A -> e
3.  B -> b
4.  B -> e

The non terminals in the grammar are: A B S 
The terminals in the grammar are: $ a b 

Firsts list: 
A : a e 
B : b e 
S : a b e 

Follows list: 
A : $ b 
B : $ 
S : $ 

Parsing Table: 
   $ a b 
A  2 1 2 
B  4 - 3 
S  0 0 0 

Input string is accepted
```
