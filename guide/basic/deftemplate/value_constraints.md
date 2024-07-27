# Slot Value Constraint Attributes

The syntax and functionality of single and multifield constraint attributes are described in detail in Section 11. Static and dynamic constraint checking for deftemplates is supported. Static checking is performed when constructs or commands using deftemplates slots are being parsed (and the specific deftemplate associated with the construct or command can be immediately determined). Template patterns used on the LHS of a rule are also checked to determine if constraint conflicts exist among variables used in more than one slot. Errors for inappropriate values are immediately signaled. References to fact‑index‑es made in commands such as **modify** and **duplicate** are considered to be ambiguous and are never checked using static checking. Static checking is always enabled. Dynamic checking is also supported. If dynamic checking is enabled, then new deftemplate facts have their values checked when created. This dynamic checking is disabled by default. This behavior can be changed using the **set‑dynamic‑constraint‑checking** function. If a violation occurs when dynamic checking is being performed, then execution will be halted.

Example

```
(deftemplate thing
    (slot name
        (type SYMBOL)
        (default ?DERIVE))
    (slot location
        (type SYMBOL)
        (default ?DERIVE))
    (slot on-top-of
        (type SYMBOL)
        (default floor))
    (slot weight
        (allowed-values light heavy)
        (default light))
    (multislot contents
        (type SYMBOL)
        (default ?DERIVE)))
```
