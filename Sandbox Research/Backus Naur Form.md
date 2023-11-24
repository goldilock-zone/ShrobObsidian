Backus-Naur Form (BNF) is a widely used notation in computer science and formal language theory for describing the syntax of programming languages and other formal languages. It was developed by John Backus and Peter Naur in the late 1950s and early 1960s and is named after them. BNF is often used in the context of defining the grammar of a language or specifying the structure of a language's expressions and statements.

BNF uses a set of production rules to define the valid syntactic structures of a language. These rules are expressed using a combination of terminal symbols, non-terminal symbols, and meta-symbols. Here are the key elements of BNF:

1. Terminal symbols: These are the basic symbols or characters that appear in the language being defined. For example, in a programming language, terminal symbols could be keywords, operators, punctuation marks, and literals (e.g., numbers and strings).

2. Non-terminal symbols: These are placeholders for syntactic categories or structures within the language. Non-terminal symbols are often represented using uppercase letters. They represent higher-level structures that can be composed of terminal and other non-terminal symbols.

3. Meta-symbols: BNF uses certain meta-symbols to represent specific elements of the grammar:
   - ::= (double colon equals): This symbol is used to define production rules. It separates a non-terminal symbol from the set of symbols that can replace it.
   - | (vertical bar or pipe): This symbol is used to indicate alternatives within a production rule. It allows for multiple valid choices for a non-terminal symbol.
   - <> (angle brackets or angle braces): These are sometimes used to enclose non-terminal symbols for clarity.

Here's a simple example of a BNF rule for defining the syntax of arithmetic expressions:

```
<expression> ::= <term> | <expression> + <term> | <expression> - <term>
<term> ::= <factor> | <term> * <factor> | <term> / <factor>
<factor> ::= <number> | (<expression>)
<number> ::= [0-9]+
```

In this example, `<expression>`, `<term>`, `<factor>`, and `<number>` are non-terminal symbols, and `+`, `-`, `*`, `/`, and `(` are terminal symbols. The rules define how arithmetic expressions are structured, with `<expression>` being the highest-level construct.

BNF is commonly used for documenting and specifying the syntax of programming languages, configuration files, markup languages (such as HTML and XML), and other formal languages. It provides a clear and concise way to describe the valid syntactic constructs of a language.

# Examples

1. BNF for Simple Arithmetic Expressions (Expanded):
   ```
   <expression> ::= <term> | <expression> + <term> | <expression> - <term>
   <term> ::= <factor> | <term> * <factor> | <term> / <factor>
   <factor> ::= <number> | (<expression>)
   <number> ::= [0-9]+
   ```

   This is an expansion of the previous example, providing more detail about the syntax of arithmetic expressions, including addition, subtraction, multiplication, division, and the use of parentheses.

2. BNF for a Simple Assignment Statement:
   ```
   <assignment> ::= <variable> = <expression>
   <variable> ::= [a-zA-Z][a-zA-Z0-9]*
   ```

   This BNF defines the syntax for a simple assignment statement where a variable is assigned a value using the "=" operator. `<variable>` represents a valid variable name, starting with a letter and followed by letters or digits.

3. BNF for a Basic HTML Element:
   ```
   <element> ::= <tag> <content> </tag>
   <tag> ::= <tagname> | <tagname> <attributes>
   <attributes> ::= <attribute> | <attribute> <attributes>
   <attribute> ::= <attrname>="value"
   <tagname> ::= [a-zA-Z][a-zA-Z0-9]* 
   <attrname> ::= [a-zA-Z][a-zA-Z0-9]*
   <content> ::= <text> | <element> | <text> <content>
   <text> ::= [^<]*
   ```

   This BNF defines the syntax for a basic HTML element, including opening and closing tags, attributes, and text content. It's a simplified representation of HTML's structure.

4. BNF for a Simple While Loop in a Programming Language:
   ```
   <while-loop> ::= while (<condition>) { <statements> }
   <condition> ::= <expression> <comparison-operator> <expression>
   <comparison-operator> ::= == | != | < | > | <= | >=
   <statements> ::= <statement> | <statement> <statements>
   <statement> ::= <assignment> | <while-loop> | <if-statement> | ...
   ```

   This BNF defines the syntax for a simple `while` loop in a programming language, including the condition, statements within the loop, and comparison operators.

5. BNF for a Simple JSON Object:
   ```
   <json-object> ::= { <json-pairs> }
   <json-pairs> ::= <json-pair> | <json-pair> , <json-pairs>
   <json-pair> ::= <string> : <json-value>
   <json-value> ::= <string> | <number> | <json-object> | <json-array> | true | false | null
   <string> ::= "([^"\\]|\\["\\/bfnrt])*"
   <number> ::= -?(0|[1-9][0-9]*)(\.[0-9]+)?([eE][+-]?[0-9]+)?
   <json-array> ::= [ <json-values> ]
   <json-values> ::= <json-value> | <json-value> , <json-values>
   ```

   This BNF defines the syntax for a simple JSON object, including key-value pairs, strings, numbers, arrays, and basic JSON data types.

These examples illustrate how BNF can be used to describe the syntax of various language constructs, ranging from arithmetic expressions to programming language constructs and data serialization formats like JSON. BNF is a versatile notation for formally specifying the structure of languages in a clear and concise manner.

BNF can be used to structure the tree form of expressions that are fundamental to functional programming languages

[[Tree form of Programming Language Expressions]]

