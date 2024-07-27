# Implied Deftemplates

Asserting or referring to an ordered fact (such as in a LHS pattern) creates an “implied” deftemplate with a single implied multifield slot named _implied_. The implied multifield slot’s name is not printed when the fact is printed. The implied deftemplate can be manipulated and examined identically to any user defined deftemplate.

Example

```
CLIPS> (clear)
CLIPS> (assert (groceries milk eggs cheese))
<Fact-1>
CLIPS> (defrule study (homework math) =>)
CLIPS> (list-deftemplates)
groceries
homework
For a total of 2 deftemplates.
CLIPS> (facts)
f-1 (groceries milk eggs cheese)
For a total of 1 fact.
CLIPS>
```
