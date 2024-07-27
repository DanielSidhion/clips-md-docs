# Defrule Construct

One of the primary methods of representing knowledge in CLIPS are rules. A **rule** is a collec­tion of conditions and the actions to be taken if the conditions are satisfied. The developer of an expert system defines the rules that describe how to solve a problem. Rules execute (or **fire**) based on the existence or non‑existence of facts or instances of user‑defined classes. CLIPS provides the mechanism (the **inference engine**) which attempts to match the rules to the cur­rent state of the system (as represented by the fact‑list‑ and instance‑list‑) and applies the actions.

Throughout this section, the term **pattern entity** will be used to refer to either a fact or an instance of a user‑defined class.
