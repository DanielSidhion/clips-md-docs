# Defining Rules

Rules are defined using the **defrule** construct.

Syntax

```
(defrule <rule-name> [<comment>]
    [<declaration>]              ; Rule Properties
    <conditional-element>*       ; Left-Hand Side (LHS)
    =>
    <action>*)                   ; Right-Hand Side (RHS)
```

Redefining a currently existing defrule causes the previous defrule with the same name to be removed even if the new definition has errors in it. The LHS is made up of a series of conditional elements (CEs) that typically consist of pattern conditional elements (or just simply patterns) to be matched against pattern entities. An implicit **and** conditional element always surrounds all the patterns on the LHS. The RHS contains a list of actions to be per­formed when the LHS of the rule is sat­isfied. In addition, the LHS of a rule may also contain declarations about the rule’s properties immediately following the rule’s name and comment. The arrow (**=>**) separates the LHS from the RHS. Actions are performed sequentially if, and only if, all condi­tional elements on the LHS are satisfied.

If no conditional elements are on the LHS, the rule will automatically be activated. If no ac­tions are on the RHS, the rule can be activated and fired but nothing will happen.

As rules are defined, they are incrementally reset. This means that CEs in newly defined rules can be satisfied by pattern entities at the time the rule is defined, in addition to pattern entities created after the rule is defined.

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate oav
    (slot object)
    (slot attribute)
    (slot value))
CLIPS>
(defrule example-rule "This is an example of a simple rule"
    (oav (object refrigerator)
        (attribute light)
        (value on))
    (oav (object refrigerator)
        (attribute door)
        (value open))
    =>
    (assert (oav (object refrigerator)
                 (attribute food)
                 (value spoiled))))
CLIPS>
(assert (oav (object refrigerator)
             (attribute light)
             (value on))
        (oav (object refrigerator)
             (attribute door)
             (value open)))
<Fact-2>
CLIPS> (agenda)
0 example-rule: f-1,f-2
For a total of 1 activation.
CLIPS> (run)
CLIPS> (facts)
f-1 (oav (object refrigerator) (attribute light) (value on))
f-2 (oav (object refrigerator) (attribute door) (value open))
f-3 (oav (object refrigerator) (attribute food) (value spoiled))
For a total of 3 facts.
CLIPS>
```
