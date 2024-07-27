# Interacting with CLIPS

CLIPS programs may be executed in three ways: interactively using a simple Read-Eval-Print Loop (REPL) interface; interactively using an Integrated Development Environment (IDE) interface; or as embedded application in which the user provides a main pro­gram and controls execution of the expert system through the CLIPS Application Programming Interface (API).

The CLIPS REPL interface is similar to a LISP or Python REPL and is portable to all environments. Stan­dard usage for the REPL is to create or edit a knowledge base using any standard text editor; save the knowledge base as one or more text files; then load, debug, and run the knowledge base using the CLIPS REPL.

Integrated Development Environments are also available for macOS, Windows, and Java. The IDEs provide an enhanced REPL that supports inline editing and a command history; dialog boxes for specifying files and directories; and debugging windows for displaying the current state of a CLIPS program. The IDEs are described in more detail in the _Interfaces Guide_.

Embedded applications are dis­cussed in the _Advanced Programming Guide_.

## Read-Eval-Print Loop

The primary method for interacting with CLIPS in a non‑embedded environment is through the CLIPS Read-Eval-Print Loop (REPL). When the “CLIPS>” prompt is displayed, CLIPS will wait for input to evaluate. Once valid input is provided and followed by pressing the return key, the input will be evaluated and the result (if any) will be printed. Any extraneous input following the valid input is then discarded. Valid input is a function call, construct, local or global variable, or constant. Function calls in CLIPS use a prefix notation—the operands to a function always appear after the function name. Entering a construct definition at the CLIPS prompt creates a new construct of the appropriate type. Both function calls and constructs use parentheses as delimiters and these must be properly balanced, otherwise the input will not be evaluated or an error will occur. Entering a global variable causes the value of the global variable to be printed. Local variables can be set at the command prompt using the bind function and retain their value until a reset or clear command is issued. Entering a local variable causes the value of the local variable to be printed. Entering a constant causes the constant to be printed (which is not very useful). Example interaction with the REPL is shown following.

```
CLIPS (6.4.1 4/8/23)
CLIPS> (+ 3 4)
7
CLIPS> (defglobal ?*x* = 3)
CLIPS> ?*x*
3
CLIPS> red
red
CLIPS> (bind ?a 5)
5
CLIPS> (+ ?a 3)
8
CLIPS> (reset)
CLIPS> ?a
[EVALUATN1] Variable a is unbound
FALSE
CLIPS>
```

First the addition function is called adding the numbers 3 and 4 to yield the result 7. A global variable `?*x*` is then defined and given the value 3. The variable `?*x*` is then entered at the prompt and its value is returned. The constant symbol _red_ is entered and returned (since a constant evaluates to itself). The local variable ?a is assigned the value 5 using the bind function. The addition function is called to add the variable ?a to the integer 3 yielding 8. The reset command is called to reset the CLIPS environment (which among other effects removes the assignment of local variables). When the variable ?a is entered at the prompt, an error occurs because the variable is no longer bound.

## Automated Command Entry and Loading

Some operating systems allow additional arguments to be specified to a program when it begins execution. When the CLIPS executable is started under such an operating system, CLIPS can be made to automatically execute a series of commands read directly from a file or to load constructs from a file. The command‑line syntax for starting CLIPS and automatically reading commands or loading constructs from a file is shown following.

Syntax

```
clips <option>*

<option> ::= -f <filename> |
             -f2 <filename> |
             -l <filename>
```

For the **`‑f`** option, `<filename>` is a file that contains CLIPS commands. If the **`exit`** command is included in the file, CLIPS will halt and the user is returned to the operat­ing system after executing the commands in the file. If an **`exit`** command is not in the file, CLIPS will enter in its interactive state after executing the commands in the file. Commands in the file should be entered exactly as they would be interactively (i.e. opening and closing parentheses must be included and a carriage return must be at the end of the command). The **`‑f`** command line option is equivalent to interactively entering a **`batch`** command as the first command to the CLIPS prompt.

The **`-f2`** option is similar to the **`-f`** option, but is equivalent to interactively entering a **`batch*`** command. The commands stored in `<filename>` are immediately executed, but the commands and their return values are not displayed as they would be for a **`batch`** command.

For the **`-l`** option, `<filename>` should be a file containing CLIPS constructs. This file will be loaded into the environment. The **`‑l`** command line option is equivalent to interactively entering a **`load`** command.

Files specified using the **`–f`** option are not processed until the CLIPS prompt appears, so these files will always be processed after files specified using the **`–f2`** and **`–l`** options.
