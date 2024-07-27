# CLIPS Object‑Oriented Language

This section gives a brief overview of the programming elements of the CLIPS Object‑Oriented Language (COOL). COOL includes elements of data abstraction and knowledge representation. This section gives an overview of COOL as a whole, incorporating the elements of both concepts.

## COOL Deviations from a Pure OOP Paradigm

In a pure OOP language, _all_ programming elements are objects which can only be manipulated via messages. In CLIPS, the definition of an object is much more constrained: floating‑point and integer numbers, symbols, strings, multifield values, external‑addresses, fact‑addresses and instances of user‑defined classes. All objects _may_ be manipulated with messages, except instances of user‑defined classes, which _must_ be. For example, in a pure OOP system, to add two numbers together, you would send the message “add” to the first number object with the second number object as an argument. In CLIPS, you may simply call the “+” function with the two numbers as arguments, or you can define message‑handlers for the NUMBER class which allow you to do it in the purely OOP fashion.

All programming elements that are not objects must be manipulated in a non‑OOP utilizing function tailored for those programming elements. For example, to print a rule, you call the **ppdefrule** command you do not send a message “print” to a rule, since it is not an object.

## Primary OOP Features

OOP systems have five primary characteristics: **abstraction**, **encapsulation**, **inheritance**, **polymorphism**, and **dynamic binding**. An abstraction is a higher level, more intuitive representation for a complex concept. Encapsulation is the process whereby the implementation details of an object are masked by a well‑defined external interface. Classes may be described in terms of other classes by use of inheritance. Polymorphism is the ability of different objects to respond to the same message in a specialized manner. Dynamic binding is the ability to defer the selection of which specific message‑handlers will be called for a message until run‑time.

The definition of new classes allows the abstraction of new data types in COOL. The slots and message‑handlers of these classes describe the properties and behavior of a new group of objects.

COOL supports encapsulation by requiring message‑passing for the manipulation of instances of user‑defined classes. An instance cannot respond to a message for which it does not have a defined message‑handler.

COOL allows the user to specify some or all of the properties and behavior of a class in terms of one or more unrelated superclasses. This process is called **multiple inheritance**. COOL uses the existing hierarchy of classes to establish a linear ordering called the **class precedence list** for a new class. Objects that are instances of this new class can inherit properties (slots) and behavior (message‑handlers) from each of the classes in the class precedence list. The word precedence implies that properties and behavior of a class first in the list override conflicting definitions of a class later in the list.

One COOL object can respond to a message in a completely different way than another object; this is polymorphism. This is accomplished by attaching message‑handlers with differing actions but which have the same name to the classes of these two objects respectively.

Dynamic binding is supported in that an object reference in a **send** function call is not bound until run‑time. For example, an instance‑name or variable might refer to one object at the time a message is sent and another at a later time.

## Instance‑set Queries and Distributed Actions

In addition to the ability of rules to directly pattern‑match on objects, COOL provides a useful query system for determining, grouping and performing actions on sets of instances of user‑defined classes that meet user‑defined criteria. The query system allows you to associate instances that are either related or not. You can simply use the query system to determine if a particular association set exists, save the set for future reference, or iterate an action over the set. An example of the use of the query system might be to find the set of all pairs of boys and girls that have the same age.
