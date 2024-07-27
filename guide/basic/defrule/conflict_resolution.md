# Conflict Resolution Strategies

The **agenda** is the list of all rules that have their conditions satisfied (and have not yet been executed). Each module has its own agenda. The agenda acts similar to a stack (the top rule on the agenda is the first one to be executed). When a rule is newly activated, its placement on the agenda is based (in order) on the following factors:

a. Newly activated rules are placed above all rules of lower salience and below all rules of higher salience.

b. Among rules of equal salience, the current conflict resolution strategy is used to determine the placement among the other rules of equal salience.

c. If a rule is activated (along with several other rules) by the same assertion or retraction of a fact, and steps a and b are unable to specify an ordering, then the rule is arbitrarily (_not randomly_) ordered in relation to the other rules with which it was activated. Note, in this respect, the order in which rules are defined has an arbitrary effect on conflict resolution (which is highly dependent upon the current underlying implementation of rules). _Do not_ depend upon this arbitrary ordering for the proper execution of your rules.

CLIPS provides seven conflict resolution strategies: depth, breadth, simplicity, complexity, lex, mea, and random. The default strategy is depth. The current strategy can be set by using the **set‑strategy** command (which will reorder the agenda based upon the new strategy).

## Depth Strategy

Newly activated rules are placed above all rules of the same salience. For example, given that fact‑a activates rule‑1 and rule‑2 and fact‑b activates rule‑3 and rule‑4, then if fact‑a is asserted before fact‑b, rule‑3 and rule‑4 will be above rule‑1 and rule‑2 on the agenda. However, the position of rule‑1 relative to rule‑2 and rule‑3 relative to rule‑4 will be arbitrary.

## Breadth Strategy

Newly activated rules are placed below all rules of the same salience. For example, given that fact‑a activates rule‑1 and rule‑2 and fact‑b activates rule‑3 and rule‑4, then if fact‑a is asserted before fact‑b, rule‑1 and rule‑2 will be above rule‑3 and rule‑4 on the agenda. However, the position of rule‑1 relative to rule‑2 and rule‑3 relative to rule‑4 will be arbitrary.

## Simplicity Strategy

Among rules of the same salience, newly activated rules are placed above all activations of rules with equal or higher specificity. The **specificity** of a rule is determined by the number of comparisons that must be performed on the LHS of the rule. Each comparison to a constant or previously bound variable adds one to the specificity. Each function call made on the LHS of a rule as part of the :, =, or test conditional element adds one to the specificity. The boolean functions **and**, **or**, and **not** do not add to the specificity of a rule, but their arguments do. Function calls made within a function call do not add to the specificity of a rule. For example, the following rule

```
(deftemplate point
    (slot x)
    (slot y)
    (slot z))

(defrule example
    (point (x ?x) (y ?y) (z ?x))
    (test (and (numberp ?x) (> ?x (+ 10 ?y)) (< ?x 100)))
    =>)
```

has a specificity of 5. The comparison to the constant item, the comparison of ?x to its previous binding, and the calls to the **numberp**, **\<**, and **\>** functions each add one to the specificity for a total of 5. The calls to the **and** and **+** functions do not add to the specificity of the rule.

## Complexity Strategy

Among rules of the same salience, newly activated rules are placed above all activations of rules with equal or lower specificity.

## LEX Strategy

Among rules of the same salience, newly activated rules are placed using the OPS5 (an early expert system tool) strategy of the same name. First the recency of the pattern entities that activated the rule is used to determine where to place the activation. Every fact and instance is marked internally with a “time tag” to indicate its relative recency with respect to every other fact and instance in the system. The pattern entities associated with each rule activation are sorted in descending order for determining placement. An activation with a more recent pattern entities is placed before activations with less recent pattern entities. To determine the placement order of two activations, compare the sorted time tags of the two activations one by one starting with the largest time tags. The comparison should continue until one activation’s time tag is greater than the other activation’s corresponding time tag. The activation with the greater time tag is placed before the other activation on the agenda.

If one activation has more pattern entities than the other activation and the compared time tags are all identical, then the activation with more time tags is placed before the other activation on the agenda. If two activations have the exact same recency, the activation with the higher specificity is placed above the activation with the lower specificity. Unlike OPS5, the _not_ conditional elements in CLIPS have pseudo time tags that are used by the LEX conflict resolution strategy. The time tag of a _not_ CE is always less than the time tag of a pattern entity, but greater than the time tag of a _not_ CE that was instantiated after the _not_ CE in question.

As an example, the following six activations have been listed in their LEX ordering (where the \* indicates the presence of a _not_ CE). Note that a fact’s time tag is not necessarily the same as it’s index (since instances are also assigned time tags), but if one fact’s index is greater than another facts’s index, then it’s time tag is also greater. For this example, assume that the time tags and indices are the same.

```
rule-6: f-1,f-4
rule-5: f-1,f-2,f-3,*
rule-1: f-1,f-2,f-3
rule-2: f-3,f-1
rule-4: f-1,f-2,*
rule-3: f-2,f-1
```

Shown following are the same activations with the fact indices sorted as they would be by the LEX strategy for comparison.

```
rule-6: f-4,f-1
rule-5: f-3,f-2,f-1,*
rule-1: f-3,f-2,f-1
rule-2: f-3,f-1
rule-4: f-2,f-1,*
rule-3: f-2,f-1
```

## MEA Strategy

Among rules of the same salience, newly activated rules are placed using the OPS5 strategy of the same name. First the time tag of the pattern entity associated with the first pattern is used to determine where to place the activation. An activation that has a first pattern with a time tag that is greater than time tag of the first pattern of another activation is placed before the other activation on the agenda. If both activations have the same time tag associated with the first pattern, then the LEX strategy is used to determine placement of the activation. Again, as with the CLIPS LEX strategy, negated patterns have pseudo time tags.

As an example, the following six activations have been listed in their MEA ordering (where the \* indicates the presence of a negated pattern).

```
rule-2: f-3,f-1
rule-3: f-2,f-1
rule-6: f-1,f-4
rule-5: f-1,f-2,f-3,*
rule-1: f-1,f-2,f-3
rule-4: f-1,f-2,*
```

## Random Strategy

Each activation is assigned a random number that is used to determine its placement among activations of equal salience. This random number is preserved when the strategy is changed so that the same ordering is reproduced when the random strategy is selected again (among activations that were on the agenda when the strategy was originally changed).

### Usage Note

A conflict resolution strategy is an implicit mechanism for specifying the order in which rules of equal salience should be executed. In early expert system tools, this was often the only mechanism provided to specify the order. Because the mechanism is implicit, it’s not possible to determine the programmer’s original intent simply by looking at the code. Rather than explicitly indicating that rule A should be executed before rule B, the order of execution is implicitly determined by the order in which facts are asserted and the complexity of the rules. The assumption one must make when examining the code is that the original programmer carefully analyzed the rules and followed the necessary conventions so that the rules execute in the appropriate sequence.

Because they require explicit declarations, the preferred mechanisms in CLIPS for ordering the execution of rules are salience and modules. Salience allows one to explicitly specify that one rule should be executed before another rule. Modules allow one to explicitly specify that all of the rules in a particular group (module) should be executed before all of the rules in a different group. Thus, when designing a program the following convention should be followed: if two rules have the same salience, are in the same module, and are activated concurrently, then the order in which they are executed should not matter. For example, the following two rules need correction because they can be activated at the same time, but the order in which they execute matters:

```
(defrule print-schedules
    (classes-scheduled)
    =>
    (assert (print-schedules)))
(defrule retry-scheduling
    ?f <- (classes-scheduled)
    (scheduling-errors)
    =>
    (retract ?f)
    (assert (retry-scheduling)))
```

Programmers should also be careful to avoid overusing salience. Trying to unravel the relationships between dozens of salience values can be just as confusing as the implicit use of a conflict resolution strategy in determining rule execution order. It’s rarely necessary to use more than five to ten salience values in a well-designed program.

Most programs should use the default conflict resolution strategy of depth. The breadth, simplicity, and complexity strategies are provided largely for academic reasons (i.e. the study of conflict resolution strategies). The lex and mea strategies are provided to help in converting OPS5 programs to CLIPS.

The random strategy is useful for testing. Because this strategy randomly orders activations having the same salience, it is useful in detecting whether the execution order of rules with the same salience effects the program behavior. Before running a program with the random strategy, first seed the random number generator using the **seed** function. The same seed value can be subsequently be used if it is necessary to replicate the results of the program run.
