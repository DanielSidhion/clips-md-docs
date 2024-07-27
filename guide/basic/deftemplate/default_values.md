# Slot Default Values

The \<default‑attribute\> specifies the value to be used for unspecified slots of a template fact when an **assert** action is performed. One of two types of default selections can be chosen: default or dynamic‑default.

The **default** attribute specifies a static default value. The specified expressions are evaluated once when the deftemplate is defined and the result is stored with the deftemplate. The result is assigned to the appropriate slot when a new template fact is asserted. If the keyword `?DERIVE` is used for the default value, then a default value is derived from the constraints for the slot (see section 11.5 for more details). By default, the default attribute for a slot is (default `?DERIVE`). If the keyword `?NONE` is used for the default value, then a value must explicitly be assigned for a slot when an assert is performed. It is an error to assert a template fact without specifying the values for the (default `?NONE`) slots.

The **default‑dynamic** attribute is a dynamic default. The specified expressions are evaluated every time a template fact is asserted, and the result is assigned to the appropriate slot.

A single‑field slot may only have a single value for its default. Any number of values may be specified as the default for a multifield slot (as long as the number of values satisfies the cardinality attribute for the slot).

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate point
    (slot x (default ?NONE))
    (slot y (type INTEGER) (default ?DERIVE))
    (slot id (default (gensym\*)))
    (slot uid (default-dynamic (gensym\*))))
CLIPS> (assert (point))
[TMPLTRHS1] Slot 'x' requires a value because of its (default ?NONE) attribute.
CLIPS> (assert (point (x 3)))
<Fact-1>
CLIPS> (assert (point (x 4)))
<Fact-2>
CLIPS> (facts)
f-1 (point (x 3) (y 0) (id gen1) (uid gen2))
f-2 (point (x 4) (y 0) (id gen1) (uid gen3))
For a total of 2 facts.
CLIPS>
```
