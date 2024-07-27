# Knowledge Representation

CLIPS provides heuristic and procedural paradigms for representing knowledge. These two paradigms are discussed in this section. Object‑oriented programming (which combines aspects of both data abstraction and procedural knowledge) is discussed in section 2.6.

## Heuristic Knowledge – Rules

One of the primary methods of representing knowledge in CLIPS is a rule. Rules are used to represent heuristics, or “rules of thumb”, which specify a set of actions to be performed for a given situation. The de­veloper of an expert system defines a set of rules that collectively work together to solve a problem. A **rule** is composed of an **antecedent** and a **consequent**. The antecedent of a rule is also referred to as the **if portion** or the **left‑hand side** (LHS) of the rule. The consequent of a rule is also referred to as the **then portion** or the **right‑hand side** (RHS) of the rule.

The antecedent of a rule is a set of **conditions** (or **conditional elements**) that must be satisfied for the rule to be applicable. In CLIPS, the conditions of a rule are satisfied based on the existence or non‑existence of specified facts in the fact‑list or specified instances of user‑defined classes in the instance‑list. One type of condition that can be specified is a **pattern**. Patterns consist of a set of restrictions that are used to determine which facts or objects satisfy the condition specified by the pattern. The process of matching facts and objects to patterns is called **pattern‑matching**. CLIPS provides a mechanism, called the **inference engine**, which automatically matches patterns against the current state of the fact‑list and instance‑list and determines which rules are applicable.

The consequent of a rule is the set of actions to be executed when the rule is applicable. The actions of applicable rules are executed when the CLIPS inference engine is instructed to begin execution of applicable rules. If more than one rule is applicable, the inference engine uses a **conflict resolution strategy** to select which rule should have its actions executed. The actions of the selected rule are executed (which may affect the list of applicable rules) and then the inference engine selects another rule and executes its actions. This process continues until no applicable rules remain.

In many ways, rules can be thought of as IF‑THEN statements found in procedural programming languages such as C and Java. However, the conditions of an IF‑THEN statement in a procedural language are only evaluated when the program flow of control is directly at the IF‑THEN statement. In contrast, rules act like WHENEVER‑THEN statements. The inference engine always keeps track of rules that have their conditions satisfied and thus rules can immediately be executed when they are applicable. In this sense, rules are similar to exception handlers found in languages such as Java.

## Procedural Knowledge

CLIPS also supports a procedural paradigm for representing knowledge. Deffunctions and generic functions allow the user to define new executable elements in CLIPS that perform a useful side‑effect or return a useful value. These new functions can be called just like the built‑in functions of CLIPS. Message‑handlers allow the user to define the behavior of objects by specifying their response to messages. Deffunctions, generic functions and message‑handlers are all procedural pieces of code specified by the user that CLIPS executes interpretively at the appropriate times. Defmodules allow a knowledge base to be partitioned.

### Deffunctions

Deffunctions allow you to define new functions in CLIPS directly (as opposed to user‑defined functions which are written in an external language such as C or Java). The body of a deffunction is a series of expressions similar to the RHS of a rule that are executed in order by CLIPS when the deffunction is called. The return value of a deffunction is the value of the last expression evaluated within the deffunction. Calling a deffunction is identical to calling any other function in CLIPS.

### Generic Functions

Generic functions are similar to deffunctions in that they can be used to define new procedural code directly in CLIPS, and they can be called like any other function. However, generic functions are much more powerful because they can be **overloaded**. A generic function will do different things depending on the types (or classes) and number of its arguments. Generic functions are comprised of multiple components called methods, where each method handles different cases of arguments for the generic function. For example, you might overload the “+” operator to do string concatenation when it is passed strings as arguments. However, the “+” operator will still perform arithmetic addition when passed numbers. There are two methods in this example: an explicit one for strings defined by the user and an implicit one which is the standard CLIPS arithmetic addition operator. The return value of a generic function is the evaluation of the last expression in the method executed.

### Object Message‑Passing

Objects are described in two basic parts: properties and behavior. Object properties are specified in terms of slots obtained from the object’s class. Object behavior is specified in terms of procedural code called message‑handlers which are attached to the object’s class. Objects are manipulated via message‑passing. For example, to cause the Rolls‑Royce object, which is an instance of the class CAR, to start its engine, the user must call the **send** function to send the message “start‑engine” to the Rolls‑Royce. How the Rolls‑Royce responds to this message will be dictated by the execution of the message‑handlers for “start‑engine” attached to the CAR class and any of its superclasses. The result of a message is similar to a function call in CLIPS: a useful return value or side‑effect.

### Defmodules

Defmodules allow a knowledge base to be partitioned. Every construct defined must be placed in a module. The programmer can explicitly control which constructs in a module are visible to other modules and which constructs from other modules are visible to a module. The visibility of facts and instances between modules can be controlled in a similar manner. Modules can also be used to control the flow of execution of rules.
