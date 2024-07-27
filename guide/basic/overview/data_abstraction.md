# Data Abstraction

There are three primary formats for representing information in CLIPS: facts, objects and global variables.

## Facts

Facts are one of the basic high‑level forms for representing information in a CLIPS system. Each **fact** represents a piece of information that has been placed in the current list of facts, called the **fact‑list**. Facts are the fundamental unit of data used by rules.

Facts may be added to the fact‑list (using the **assert** command), removed from the fact‑list (using the **retract** command), modified (using the **modify** command), or duplicated (using the **duplicate** command) through explicit user interaction or as a CLIPS program executes. If a fact is asserted into the fact‑list that exactly matches an already existing fact, the new assertion will be ignored (however, this behavior can be changed using the **set-fact-duplication** function).

Some commands, such as the **retract**, **modify**, and **duplicate** commands, require a fact to be specified. A fact can be specified either by **fact‑index** or **fact‑address**. Whenever a fact is asserted it is given a unique integer index called a fact‑index. Fact‑indices start at one and are incremented by one for each new fact. When a fact is modified, its fact-index remains unchanged. Whenever a **reset** or **clear** command is given, the fact‑indices restart at one. A fact may also be specified through the use of a fact‑address. A fact‑address can be obtained by capturing the return value of commands which return fact addresses (such as **assert**, **modify**, and **duplicate**) or by binding a variable to the fact address of a fact which matches a pattern on the LHS of a rule.

A **fact identifier** is a shorthand notation for displaying a fact. It consists of the character “f”, followed by a dash, followed by the fact‑index of the fact. For example, f‑10 refers to the fact with fact‑index 10.

A fact is stored in one of two formats: ordered or non‑ordered.

### Ordered Facts

**Ordered facts** consist of a symbol followed by a sequence of zero or more fields separated by spaces and delimited by an opening parenthesis on the left and a closing parenthesis on the right. The first field of an ordered fact specifies a “relation” that applies to the remaining fields in the ordered fact. For example, (father‑of jack bill) states that bill is the father of jack.

Some examples of ordered facts are shown following.

```
(the pump is on)

(altitude is 10000 feet)

(grocery-list bread milk eggs)
```

Fields in a non‑ordered fact may be of any of the primitive data types (with the exception of the first field which must be a symbol), and no restriction is placed on the ordering of fields. The following symbols are reserved and should not be used as the _first_ field in any fact (ordered or non‑ordered): _test_, _and_, _or_, _not_, _declare_, _logical_, _object_, _exists_, and _forall_. These words are reserved only when used as a deftemplate name (whether explicitly defined or implied). These symbols may be used as slot names, however, this is not recommended.

### Non‑ordered Facts

Ordered facts encode information positionally. To access that information, a user must know not only what data is stored in a fact but which position contains the data. **Non‑ordered (or deftemplate) facts** provide the user with the ability to abstract the structure of a fact by assign­ing names to each field in the fact. The **deftemplate** construct is used to create a template that can then be used to access fields by name. The deftemplate construct is analogous to a structure definition in C.

The deftemplate construct allows the name of a template to be defined along with zero or more definitions of **slots**. Unlike ordered facts, the slots of a deftemplate fact may be constrained by type, value, and numeric range. In addition, default values can be specified for a slot. A slot consists of an opening parenthesis followed by the name of the slot, zero or more fields, and a closing parenthesis. Note that slots may not be used in an ordered fact and that information in a deftemplate fact may not be referenced positionally.

Deftemplate facts are distinguished from ordered facts by the first field within the fact. The first field of all facts must be a symbol, however, if that symbol corresponds to the name of a deftemplate, then the fact is a deftemplate fact. The first field of a deftemplate fact is followed by a list of zero or more slots. As with ordered facts, deftemplate facts are enclosed by an opening parenthesis on the left and a closing parenthesis on the right.

Some examples of deftemplate facts are shown following.

```
(client (name "Joe Brown") (id X9345A))

(point-mass (x-velocity 100) (y-velocity -200))

(class (teacher "Martha Jones") (#-students 30) (Room "37A"))

(grocery-list (#-of-items 3) (items bread milk eggs))
```

Note that the order of slots in a deftemplate fact is not important. For example the following facts are all identical:

```
(class (teacher "Martha Jones") (#-students 30) (Room "37A"))

(class (#-students 30) (teacher "Martha Jones") (Room "37A"))

(class (Room "37A") (#-students 30) (teacher "Martha Jones"))
```

In contrast, note that the following ordered fact _are not_ identical.

```
(class "Martha Jones" 30 "37A")
(class 30 "Martha Jones" "37A")
(class "37A" 30 "Martha Jones")
```

In addition to being asserted and retracted, deftemplate facts can also be modified and duplicated (using the **modify** and **duplicate** commands). Modifying a fact changes a set of specified slots within that fact. Duplicating a fact creates a new fact identical to the original fact and then changes a set of specified slots within the new fact. The benefit of using the modify and duplicate commands is that slots which don’t change, don’t have to be specified.

### Initial Facts

The **deffacts** construct allows a set of _a priori_ or initial knowledge to be specified as a collection of facts. When the CLIPS environment is reset (using the **reset** command) every fact specified within a deffacts construct in the CLIPS knowledge base is added to the fact‑list.

## Objects

An **object** in CLIPS is defined to be a symbol, a string, a floating‑point or integer number, a multifield value, an external‑address, or an instance of a user‑defined class. Objects are described in two basic parts: properties and behavior. A **class** is a template for common properties and behavior of objects that are **instances** of that class. Some examples of objects and their classes are:

| **Object (Printed Representation)** | **Class**                  |
| ----------------------------------- | -------------------------- |
| Rolls-Royce                         | SYMBOL                     |
| "Rolls-Royce"                       | STRING                     |
| 8.0                                 | FLOAT                      |
| 8                                   | INTEGER                    |
| (8.0 Rolls-Royce 8 \[Rolls-Royce\]) | MULTIFIELD                 |
| \<Pointer-00CF61AB\>                | EXTERNAL-ADDRESS           |
| \[Rolls-Royce\]                     | CAR (a user-defined class) |

Objects in CLIPS are split into two important categories: primitive types and instances of _user‑defined_‑classes. These two types of objects differ in the way they are referenced, created and deleted as well as how their properties are specified.

Primitive type objects are referenced simply by giving their value, and they are created and deleted implicitly by CLIPS as they are needed. Primitive type objects have no names or slots, and their classes are predefined by CLIPS. The behavior of primitive type objects is like that of instances of user‑defined classes, however, in that you can define message‑handlers and attach them to the primitive type classes. It is anticipated that primitive types will not be used often in an object‑oriented programming (OOP) context; the main reason classes are provided for them is for use in generic functions. Generic functions use the classes of their arguments to determine which methods to execute.

An instance of a user‑defined class is referenced by name or address, and they are created and deleted explicitly via messages and special functions. The properties of an instance of a _user‑defined_ class are expressed by a set of slots, which the object obtains from its class. As previously defined, slots are named single field or multifield values. For example, the object Rolls‑Royce is an instance of the class CAR. One of the slots in class CAR might be “price”, and the Rolls‑Royce object’s value for this slot might be $75,000.00. The behavior of an object is specified in terms of procedural code called message‑handlers, which are attached to the object’s class. All instances of a user‑defined class have the same set of slots, but each instance may have different values for those slots. However, two instances that have the same set of slots do not necessarily belong to the same class, since two different classes can have identical sets of slots.

The primary difference between object slots and template (or non‑ordered) facts is the notion of inheritance. Inheritance allows the properties and behavior of a class to be described in terms of other classes. COOL supports multiple inheritance: a class may directly inherit slots and message‑handlers from more than one class. Since inheritance is only useful for slots and message‑handlers, it is often not meaningful to inherit from one of the primitive type classes, such as MULTIFIELD or NUMBER. This is because these classes cannot have slots and usually do not have message‑handlers.

### Initial Objects

The **definstances** construct allows a set of _a priori_ or initial knowledge to be specified as a collection of instances of user‑defined classes. When the CLIPS environment is reset (using the **reset** command) every instance specified within a definstances construct in the CLIPS knowledge base is added to the instance‑list.

## Global Variables

The **defglobal** construct allows variables to be defined which are global in scope throughout the CLIPS environment. That is, a global variable can be accessed anywhere in the CLIPS environment and retains its value independent of other constructs. In contrast, some constructs (such as defrule and deffunction) allow local variables to be defined within the definition of the construct. These local variables can be referred to within the construct, but have no meaning outside the construct. A CLIPS global variable is similar to global variables found in procedural programming languages such as C and Java.
