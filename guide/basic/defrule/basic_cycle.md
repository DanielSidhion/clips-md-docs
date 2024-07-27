# Basic Cycle Of Rule Execution

Once a knowledge base (in the form of rules) is built and the fact‑list and instance‑list is prepared, CLIPS is ready to execute rules. In a conventional language the programmer explicitly defines the starting point, the stopping point, and the sequence of operations. With CLIPS, the program flow does not need to be defined explicitly. The knowledge (rules) and the data (facts and instances) are separated, and the inference engine pro­vided by CLIPS is used to apply the knowledge to the data. The basic execution cycle is as follows:

a. If the rule firing limit has been reached or there is no current focus, then execution is halted. Otherwise, the top rule on the agenda of the module that is the current focus is selected for execution. If there are no rules on that agenda, then the current focus is removed from the focus stack and the current focus becomes the next module on the focus stack. If the focus stack is empty, then execution is halted, otherwise step _a_ is executed again.

b. The right‑hand side (RHS) actions of the selected rule are executed. The use of the **return** function on the RHS of a rule may remove the current focus from the focus stack. The number of rules fired is incremented for use with the rule firing limit.

c. As a result of step b, rules may be **activated** or **deactivated**. Activated rules (those rules whose conditions are currently satisfied) are placed on the **agenda** of the module in which they are defined. The placement on the agenda is determined by the **salience** of the rule and the current **conflict resolution strategy**. Deactivated rules are removed from the agenda. If the activations item is being watched (as a result of the **watch** command), then an informational message will be displayed each time a rule is activated or deactivated.

d. If **dynamic salience** is being used (see the **set-salience-evaluation** command), the salience values for all rules on the agenda are reevaluated. Repeat the cycle beginning with step a.
