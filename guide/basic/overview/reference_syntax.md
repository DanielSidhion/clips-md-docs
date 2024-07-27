# Reference Manual Syntax

Terminology is used throughout this manual to describe the syntax of CLIPS constructs and functions. Plain words or characters (including parentheses) are to be typed exactly as they appear. Sequences of words enclosed in single‑angle brackets (called terms or non‑terminal symbols), such as `<string>`, represent a single entity of the named class of items to be supplied by the user. A non‑terminal symbol followed by a \*, represents zero or more entities of the named class of items. A non‑terminal symbol followed by a +, represents one or more entities of the named class of items. A \* or + by itself is to be typed as it appears. Vertical and horizontal ellipsis (three dots arranged respectively vertically and horizontally) are also used between non‑terminal symbols to indicate the occurrence of one or more entities. A term enclosed within square brackets, such as `[<comment>]`, is optional (i.e. it may or may not be included). Vertical bars indicate a choice between multiple terms. White spaces (tabs, spaces, carriage re­turns) are used by CLIPS only as delimiters between terms and are ignored otherwise (unless inside double quotes). The ::= symbol is used to indicate how a non‑terminal symbol can be replaced. For example, the following syntax description indicates that a `<lexeme>` can be replaced with either a `<symbol>` or a `<string>`.

```
<lexeme> ::= <symbol> | <string>
```

A complete BNF listing for CLIPS constructs along with some commonly used replacements for non‑terminal symbols are listed in appendix G.
