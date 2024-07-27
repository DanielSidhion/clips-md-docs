# Basic Programming Elements

CLIPS provides three basic elements for writing programs: primitive data types, functions for manipulating data, and constructs for adding to a knowledge base.

## Data Types

CLIPS provides eight primitive data types for representing information. These types are **float**, **integer**, **symbol**, **string**, **external‑address**, **fact‑address**, **instance‑name** and **instance‑address**. Numeric information can be represented using floats and integers. Symbolic information can be represented using symbols and strings.

A **number** consists _only_ of digits (0‑9), a decimal point (.), a sign (+ or ‑), and, optionally, an (e) for exponential notation with its corresponding sign. A number is either stored as a float or an integer. Any number consisting of an optional sign followed by only digits is stored as an **integer** (represented internally by CLIPS as a C long long integer). All other numbers are stored as **floats** (represented internally by CLIPS as a C double‑precision float). The number of significant digits will de­pend on the machine implementation. Roundoff errors also may occur, again depend­ing on the machine implementation. As with any computer language, care should be taken when comparing floating‑point values to each other or comparing integers to floating‑point values. Some examples of integers are

```
237 15 +12 -32
```

Some examples of floats are

```
237e3 15.09 +12.0 -32.3e-7
```

Specifically, integers use the following format:

```
<integer> ::= [+ | -] <digit>+

<digit> ::= 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9
```

Floating point numbers use the following format:

```
<float> ::= <integer> <exponent> |
            <integer> . [<exponent>] |
            . <unsigned integer> [<exponent>] |
            <integer> . <unsigned integer> [<exponent>]

<unsigned-integer> ::= <digit>+

<exponent> ::= e | E <integer>
```

A sequence of characters which does not exactly follow the format of a number is treated as a symbol.

A **symbol** in CLIPS is any sequence of characters that starts with any printable ASCII character and is followed by zero or more printable ASCII characters. When a delimiter is found, the symbol is ended. The following characters act as **delimiters**: any non‑printable ASCII character (including spaces, tabs, carriage returns, and line feeds), a double quote, opening and closing parentheses “(” and “)”, an ampersand “&”, a vertical bar “|”, a less than “<”, and a tilde “~”. A semicolon “;” starts a CLIPS comment and also acts as a de­limiter. Delimiters may not be included in symbols with the exception of the “<“ character which may be the first character in a symbol. In addition, a symbol may not begin with either the “?” character or the “$?” sequence of characters (although a symbol may contain these characters). These characters are reserved for variables. CLIPS is case sensitive (i.e. uppercase letters will match only uppercase let­ters). Note that numbers are a special case of symbols (i.e. they satisfy the definition of a symbol, but they are treated as a different data type). Some simple examples of symbols are

```
red Hello B76-HI bad_value

127A 456-93-039 @+=-% 2each
```

A **string** is a set of characters that starts with a double quote (") and is followed by zero or more printable characters. A string ends with double quotes. Double quotes may be embedded within a string by placing a backslash (\\) in front of the character. A backslash may be embedded by placing two consecutive back­slash characters in the string. Some examples are

```
"red" "a and b" "1 number" "a\"quote"
```

Note that the string “abcd" is not the same as the symbol _abcd_. They both contain the same characters, but are of different types. The same holds true for the instance name `[abcd]`.

An **external‑address** is the address of an external data structure returned by a function (written in a language such as C or Java) that has been integrated with CLIPS. This data type can only be created by calling a function (i.e. it is not possible to specify an external‑address using text). In the basic version of CLIPS (which has no user defined external functions), it is not possible to create this data type. External‑addresses are discussed in further detail in the _Advanced Programming Guide_;. Within CLIPS, the printed representation of an external‑address is

```
<Pointer-C-XXXXXX>
```

where XXXXXX is the external‑address.

A **fact** is a list of primitive values that are either referenced positionally (ordered facts) or by name (non‑ordered or template facts). Facts are referred to by index or fact-address. The printed format of a **fact‑address** is:

```
<Fact-XXX>
```

where XXX is the fact‑index.

An **instance** is an **object** that is an instantiation or specific example of a **class**. Objects in CLIPS are defined to be floats, integers, symbols, strings, multifield values, external‑addresses, fact‑addresses, and instances of a user‑defined class. A user‑defined class is created using the **defclass** construct. An instance of a user‑defined class is created with the **make‑instance** function, and such an instance can be referred to uniquely by address. An **instance‑name** is formed by enclosing a symbol within left and right brackets. Thus, pure symbols may not be surrounded by brackets. If the CLIPS Object Oriented Language (COOL) is not included in a particular CLIPS configuration, then brackets may be wrapped around symbols. Some examples of instance‑names are:

```
[pump-1] [red] [+++] [123-890]
```

Note that the brackets are not part of the name of the instance; they merely indicate that the enclosed symbol is an instance‑name. An **instance‑address** can only be obtained by binding the return value of a function called **instance‑address** or by binding a variable to an instance matching an object pattern on the LHS of a rule (i.e., it is not possible to specify an instance‑address by typing the value). A reference to an instance of a user‑defined class can either be by name or address. Within CLIPS, the printed representation of an instance‑address is

```
<Instance-XXX>
```

where XXX is the name of the instance.

In CLIPS, a placeholder that has a value (one of the primitive data types) is referred to as a **field**. The primitive data types are referred to as **single‑field values**. A **constant** is a non‑varying single-field value directly expressed as a series of characters (which means that external‑addresses, fact‑addresses and instance‑addresses cannot be expressed as constants because they can only be obtained through function calls and variable bindings). A **multifield value** is a sequence of zero or more single-field values. When displayed by CLIPS, multifield values are enclosed in parentheses. Collectively, single and multifield values are referred to as **values**. Some examples of multifield values are

```
(a) (1 blue red) () (x 3.0 "red" 567)
```

Note that the multifield value `(a)` is not the same as the single field value `a`. Multifield values are created either by calling functions which return multifield values, by using wildcard arguments in a deffunction, object message‑handler, or method, or by binding variables during the pattern‑matching process for rules. In CLIPS, a **variable** is a symbolic location that is used to store values. Variables are used by many of the CLIPS constructs (such as defrule, deffunction, defmethod, and defmessage‑handler) and their usage is explained in the sections describing each of these constructs.

## Functions

A **function** in CLIPS is a piece of executable code identified by a specific name which returns a useful value or performs a useful side effect (such as displaying information). Throughout the CLIPS documentation, the word function is generally used to refer only to functions which return a value (whereas commands and actions are used to refer to functions which have a side effect but generally do not return a value).

There are several types of functions. **User defined functions** and **system defined functions** are pieces of code that have been written in an external language (such as C, Java, or C#) and linked with the CLIPS environment. System defined functions are those functions that have been defined internally by the CLIPS environment. User defined functions are functions that have been defined externally of the CLIPS environment. A complete list of system defined functions can be found in appendix H.

The **deffunction** construct allows users to define new functions directly in the CLIPS environment using CLIPS syntax. Functions defined in this manner appear and act like other functions, however, instead of being directly executed (as code written in an external language would be) they are interpreted by the CLIPS environment.

Generic functions can be defined using the **defgeneric** and **defmethod** constructs. Generic functions allow different pieces of code to be executed depending upon the arguments passed to the generic function. Thus, a single function name can be **overloaded** with more than one piece of code.

Function calls in CLIPS use a prefix notation – the arguments to a function always appear after the function name. Function calls begin with a left parenthesis, followed by the name of the function, then the arguments to the function follow (each argument separated by one or more spaces). Arguments to a function can be primitive data types, variables, or another function call. The function call is then closed with a right parenthesis.

Example

```
CLIPS> (+ 3 4 5)
12
CLIPS> (\* 5 6.0 2)
60.0
CLIPS> (+ 3 (\* 8 9) 4)
79
CLIPS> (\* 8 (+ 3 (\* 2 3 4) 9) (\* 3 4))
3456
CLIPS>
```

While a function refers to a piece of executable code identified by a specific name, an **expression** refers to a function which has its arguments specified (which may or may not be functions calls as well). Thus the previous example contains expressions which make calls to the \* and + functions.

## Constructs

Several defining **constructs** appear in CLIPS: **defmodule**, **defrule**, **deffacts**, **deftemplate**, **defglobal**, **deffunction**, **defclass**, **definstances**, **defmessage‑handler**, **defgeneric**, and **defmethod**. All constructs in CLIPS are surrounded by parentheses. The construct opens with a left parenthe­sis and closes with a right parenthesis. Defining a construct differs from calling a function primarily in effect. Typically a function call leaves the CLIPS environment unchanged (with some notable exceptions such as resetting or clearing the environment or opening a file). Defining a construct, however, is explicitly intended to alter the CLIPS environment by adding to the CLIPS knowledge base. Unlike function calls, constructs never have a return value.

As with any programming language, it is highly beneficial to comment CLIPS code. All constructs (with the exception of defglobal) allow a comment directly following the construct name. Comments also can be placed within CLIPS code by using a semicolon (;). Everything from the semicolon until the next return character will be ignored by CLIPS. If the semicolon is the first character in the line, the entire line will be treated as a comment. Semicolon commented text is not saved by CLIPS when loading constructs (however, the optional comment string within a construct is saved).
