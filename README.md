# LexLuthor

a lexer (and a project for regex?)

_remember: the coder who has a problem, and decides to solve it with regex, now has TWO problems._

Build a `Lexer` class that can read an input String, and produces an ArrayList of `Token`.

A __Lexer__, short for _Lexical Analyzer_, is a program that transforms a sequence of 
characters (like source code or HTML) into a sequence of tokens. 
These tokens are meaningful character strings, such as identifiers, keywords, literals, and operator symbols.

The process of lexical analysis involves scanning the input for patterns that match the grammar 
for a programming language and categorizing them as the appropriate token types.

Tokens are then processed further by a range of tools, even _compilers_.

The class `LexLuthor` should load the testdata files and `lex()` each one 
using the `Lexer` class which implements `LexerIdea`.

```java
interface LexerIdea {
    void setTextBuffer(String buffer);
    int getCurrentOffset();
    int getCurrentLineNumber();
    Token getNextToken();
}
```

The test data is simple HTML in `testdata/`.
There a handful of different test data files of increasing complexity.
Scan each file, creating tokens as you go.
Tokens need to be one of the six enumerated types.
The tags (keywords) you need to be able to validate are:

- html
- head
- body
- p
- div
- strong
- em
- ul
- li

The output should be a nicely formatted list of the token arraylist. (With the text from inside the tags as well).

### Trees

Extra credit, put it into a Tree. 
Think about it, an HTML file is like a tree, the tags are nested.
The `html` tag has `head` and `body` in it, and `body` has a number of even deeper nested tags.
A Tree is a great data structure to record all this structure into.
(_Yes, Great Question, the JavaScript DOM is a Tree!_)

Now, from text (HTML) file input to a tree.
Well, you first need to scan (lex) the input HTML (text) into an array list of tokens.
Then you need to loop thru the token list and create a tree from the token list.

How do you know when you create a child? well, if you have seen an `html` open tag, and the next teg is not a
close tag `\html`, then it's a child tag of `html`.
Does it feel recursive? yes, it can be.

(Wait, what, Extra-credit? No, there is not such thing is there. Do it now, or do it in the next lab.)
Here is a pseudo-code-tree, just for you!

```java
class Tree
    Node data
    ArrayList<Node> children

    Tree()

    - addNode(parent, node)
            
    - traverseInOrder(node)
    // would do something like:

    // if node is not null
    //    traverseInOrder(node.left)
    //    print(" " + node.value)
    //    traverseInOrder(node.right)

    // If we call this method, the console output will show the in-order traversal
```

Why into a Tree? Well, aren't you the __curious__ pseudo-Zipcoder.

Hmm. What's this, there are [Notes](notes.md)?
