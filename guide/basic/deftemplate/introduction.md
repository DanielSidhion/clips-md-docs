# Deftemplate Construct

Ordered facts encode information positionally. To access that information, a user must know not only what data is stored in a fact but also which field contains the data. Non‑ordered (or deftemplate) facts provide the user with the ability to abstract the structure of a fact by assign­ing names to each field found within the fact. The **deftemplate** construct is used to create a template that can then be used by non‑ordered facts to access fields of the fact by name. The deftemplate construct is analogous to a record or structure definition in programming languages such as C.

Syntax

```
(deftemplate <deftemplate-name> [<comment>]
    <slot-definition>*)

<slot-definition> ::= <single-slot-definition> |
                      <multislot-definition>

<single-slot-definition> ::= (slot <slot-name>
                                 <template-attribute>*)

<multislot-definition> ::= (multislot <slot-name>
                               <template-attribute>*)

<template-attribute> ::= <default-attribute> |
                         <constraint-attribute>

<default-attribute>
                ::= (default ?DERIVE | ?NONE | <expression>*) |
                    (default-dynamic <expression>*)
```

Redefining a deftemplate will result in the previous definition being discarded. A deftemplate can not be redefined while it is being used (for example, by a fact or pattern in a rule). A deftemplate can have any number of single or multifield slots. CLIPS always enforces the single and multifield definitions of the deftemplate. For example, it is an error to store (or match) multiple values in a single-field slot.

Example

```
(deftemplate thing
    (slot name)
    (slot location)
    (slot on-top-of)
    (slot weight)
    (multislot contents))
```
