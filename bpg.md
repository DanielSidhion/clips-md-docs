# Reference Manual

## Volume I

## Basic Programming Guide

## Version 6. 4.

Copyright © 20 23 Secret Society Software, LLC

## CLIPS Basic Programming Guide i

##### CONTENTS

License Information ................................................................................................................... xiv

         - Version 6.4.1 April 8th CLIPS Basic Programming Guide

- Section 1: Introduction Preface ...........................................................................................................................................xv
- Section 2: CLIPS Overview...........................................................................................................
  - 2.1 Interacting with CLIPS
    - 2.1.1 Read-Eval-Print Loop
    - 2.1.2 Automated Command Entry and Loading
  - 2.2 Reference Manual Syntax
  - 2.3 Basic Programming Elements
    - 2.3.1 Data Types
    - 2.3.2 Functions
    - 2.3.3 Constructs
  - 2.4 Data Abstraction
    - 2.4.1 Facts
    - 2.4.2 Objects
    - 2.4.3 Global Variables
  - 2.5 Knowledge Representation
    - 2.5.1 Heuristic Knowledge – Rules
    - 2.5.2 Procedural Knowledge
  - 2.6 CLIPS Object-Oriented Language
    - 2.6.1 COOL Deviations from a Pure OOP Paradigm
    - 2.6.2 Primary OOP Features
    - 2.6.3 Instance-set Queries and Distributed Actions
- Section 3: Deftemplate Construct
  - 3.1 Slot Default Values
  - 3.2 Slot Default Constraints for Pattern-Matching
  - 3.3 Slot Value Constraint Attributes
  - 3.4 Implied Deftemplates
- Section 4: Deffacts Construct
- Section 5: Defrule Construct
  - 5.1 Defining Rules
  - 5.2 Basic Cycle Of Rule Execution
  - 5.3 Conflict Resolution Strategies
    - 5.3.1 Depth Strategy ii Table of Contents
    - 5.3.2 Breadth Strategy........................................................................................................
    - 5.3.3 Simplicity Strategy....................................................................................................
    - 5.3.4 Complexity Strategy
    - 5.3.5 LEX Strategy
    - 5.3.6 MEA Strategy
    - 5.3.7 Random Strategy
  - 5.4 LHS Syntax
    - 5.4.1 Pattern Conditional Element
    - 5.4.2 Test Conditional Element
    - 5.4.3 Or Conditional Element
    - 5.4.4 And Conditional Element
    - 5.4.5 Not Conditional Element
    - 5.4.6 Exists Conditional Element.......................................................................................
    - 5.4.7 Forall Conditional Element
    - 5.4.8 Logical Conditional Element
    - 5.4.9 Automatic Replacement of LHS CEs
    - 5.4.10 Declaring Rule Properties
- Section 6: Defglobal Construct
- Section 7: Deffunction Construct
- Section 8: Generic Functions
  - 8.1 Note on the Use of the Term Method.................................................................................
  - 8.2 Performance Penalty of Generic Functions
  - 8.3 Order Dependence of Generic Function Definitions
  - 8.4 Defining a New Generic Function
    - 8.4.1 Generic Function Headers.........................................................................................
    - 8.4.2 Method Indices..........................................................................................................
    - 8.4.3 Method Parameter Restrictions
    - 8.4.4 Method Wildcard Parameter
  - 8.5 Generic Dispatch
    - 8.5.1 Applicability of Methods Summary..........................................................................
    - 8.5.2 Method Precedence
    - 8.5.3 Shadowed Methods
    - 8.5.4 Method Execution Errors
    - 8.5.5 Generic Function Return Value
- Section 9: CLIPS Object Oriented Language
  - 9.1 Background
  - 9.2 Predefined System Classes
  - 9.3 Defclass Construct
    - 9.3.1 Multiple Inheritance
    - 9.3.2 Class Specifiers CLIPS Basic Programming Guide iii
    - 9.3.3 Slots...........................................................................................................................
    - 9.3.4 Message-handler Documentation............................................................................
  - 9.4 Defmessage-handler Construct
    - 9.4.1 Message-handler Parameters
    - 9.4.2 Message-handler Actions
    - 9.4.3 Daemons
    - 9.4.4 Predefined System Message-handlers.....................................................................
  - 9.5 Message Dispatch
    - 9.5.1 Applicability of Message-handlers
    - 9.5.2 Message-handler Precedence
    - 9.5.3 Shadowed Message-handlers
    - 9.5.4 Message Execution Errors
    - 9.5.5 Message Return Value
  - 9.6 Manipulating Instances
    - 9.6.1 Creating Instances
    - 9.6.2 Reinitializing Existing Instances.............................................................................
    - 9.6.3 Reading Slots
    - 9.6.4 Setting Slots
    - 9.6.5 Deleting Instances
    - 9.6.6 Delayed Pattern-Matching When Manipulating Instances
    - 9.6.7 Modifying Instances................................................................................................
    - 9.6.8 Duplicating Instances
  - 9.7 Instance-set Queries and Distributed Actions
    - 9.7.1 Instance-set Definition
    - 9.7.2 Instance-set Determination
    - 9.7.3 Query Definition
    - 9.7.4 Distributed Action Definition
    - 9.7.5 Scope in Instance-set Query Functions
    - 9.7.6 Errors during Instance-set Query Functions
    - 9.7.7 Halting and Returning Values from Query Functions
    - 9.7.8 Instance-set Query Functions
- Section 10: Defmodule Construct
  - 10.1 Defining Modules
  - 10.2 Specifying a Construct’s Module...................................................................................
  - 10.3 Specifying Modules
  - 10.4 Importing and Exporting Constructs
    - 10.4.1 Exporting Constructs
    - 10.4.2 Importing Constructs
  - 10.5 Importing and Exporting Facts and Instances
    - 10.5.1 Specifying Instance-Names
  - 10.6 Modules and Rule Execution
- Section 11: Constraint Attributes iv Table of Contents
  - 11.1 Type Attribute
  - 11.2 Allowed Constant Attributes..........................................................................................
  - 11.3 Range Attribute
  - 11.4 Cardinality Attribute
  - 11.5 Deriving a Default Value From Constraints
  - 11.6 Constraint Violation Examples
- Section 12: Actions And Functions
  - 12.1 Predicate Functions
    - 12.1.1 Testing For Numbers
    - 12.1.2 Testing For Floats
    - 12.1.3 Testing For Integers
    - 12.1.4 Testing For Strings Or Symbols
    - 12.1.5 Testing For Strings
    - 12.1.6 Testing For Symbols
    - 12.1.7 Testing For Even Numbers
    - 12.1.8 Testing For Odd Numbers
    - 12.1.9 Testing For Multifield Values
    - 12.1.10 Testing For External-Addresses
    - 12.1.11 Comparing for Equality
    - 12.1.12 Comparing for Inequality
    - 12.1.13 Comparing Numbers for Equality
    - 12.1.14 Comparing Numbers for Inequality
    - 12.1.15 Greater Than Comparison
    - 12.1.16 Greater Than or Equal Comparison
    - 12.1.17 Less Than Comparison
    - 12.1.18 Less Than or Equal Comparison
    - 12.1.19 Boolean And
    - 12.1.20 Boolean Or
    - 12.1.21 Boolean Not
  - 12.2 Multifield Functions.......................................................................................................
    - 12.2.1 Creating Multifield Values
    - 12.2.2 Specifying an Element
    - 12.2.3 Finding an Element
    - 12.2.4 Comparing Multifield Values
    - 12.2.5 Deletion of Fields in Multifield Values
    - 12.2.6 Creating Multifield Values from Strings.
    - 12.2.7 Creating Strings from Multifield Values
    - 12.2.8 Extracting a Sub-sequence from a Multifield Value.............................................
    - 12.2.9 Replacing Fields within a Multifield Value
    - 12.2.10 Inserting Fields within a Multifield Value
    - 12.2.11 Getting the First Field from a Multifield Value
  - 12.2.12 Getting All but the First Field from a Multifield Value...................................... CLIPS Basic Programming Guide v
  - 12.2.13 Determining the Number of Fields in a Multifield Value...................................
  - 12.2.14 Deleting Specific Values within a Multifield Value
  - 12.2.15 Replacing Specific Values within a Multifield Value
  - 12.2.16 Creating the Union of Multifield Values
  - 12.2.17 Creating the Intersection of Multifield Values
  - 12.2.18 Creating the Difference of Multifield Values
- 12.3 String Functions
  - 12.3.1 String Concatenation
  - 12.3.2 Symbol Concatenation
  - 12.3.3 Taking a String Apart............................................................................................
  - 12.3.4 Searching a String
  - 12.3.5 Evaluating a Function within a String
  - 12.3.6 Evaluating a Construct within a String
  - 12.3.7 Converting a String to Uppercase
  - 12.3.8 Converting a String to Lowercase.........................................................................
  - 12.3.9 Comparing Two Strings
  - 12.3.10 Determining the Length of a String
  - 12.3.11 Checking the Syntax of a Construct or Function Call within a String................
  - 12.3.12 Converting a String to a Field
  - 12.3.13 Replacing Portions of a String
- 12.4 I/O Functions
  - 12.4.1 Opening a File
  - 12.4.2 Closing a File
  - 12.4.3 Printing
  - 12.4.4 Reading a Single Field
  - 12.4.5 Reading an Entire Line
  - 12.4.6 Formatted Printing
  - 12.4.7 Renaming a File
  - 12.4.8 Removing a File
  - 12.4.9 Reading a Character
  - 12.4.10 Unreading a Character
  - 12.4.11 Reading a Number
  - 12.4.12 Setting the Locale
  - 12.4.13 Flushing Output
  - 12.4.14 Rewinding the File Position
  - 12.4.15 Retrieving the File Position
  - 12.4.16 Setting the File Position
  - 12.4.17 Changing the Current Directory..........................................................................
- 12.5 Math Functions
  - 12.5.1 Addition
  - 12.5.2 Subtraction
  - 12.5.3 Multiplication
  - 12.5.4 Division vi Table of Contents
  - 12.5.5 Integer Division
  - 12.5.6 Maximum Numeric Value
  - 12.5.7 Minimum Numeric Value
  - 12.5.8 Absolute Value......................................................................................................
  - 12.5.9 Convert To Float
  - 12.5.10 Convert To Integer
  - 12.5.11 Trigonometric Functions
  - 12.5.12 Convert From Degrees to Grads
  - 12.5.13 Convert From Degrees to Radians
  - 12.5.14 Convert From Grads to Degrees
  - 12.5.15 Convert From Radians to Degrees
  - 12.5.16 Return the Value of π
  - 12.5.17 Square Root
  - 12.5.18 Power
  - 12.5.19 Exponential
  - 12.5.20 Logarithm
  - 12.5.21 Logarithm Base
  - 12.5.22 Round
  - 12.5.23 Modulus
- 12.6 Procedural Functions
  - 12.6.1 Binding Variables
  - 12.6.2 If...then...else Function..........................................................................................
  - 12.6.3 While
  - 12.6.4 Loop-for-count
  - 12.6.5 Progn
  - 12.6.6 Progn$
  - 12.6.7 Return
  - 12.6.8 Break
  - 12.6.9 Switch
  - 12.6.10 Foreach
- 12.7 Miscellaneous Functions
  - 12.7.1 Gensym
  - 12.7.2 Gensym\*
  - 12.7.3 Setgen
  - 12.7.4 Random
  - 12.7.5 Seed
  - 12.7.6 Time
  - 12.7.7 Determining the Restrictions for a Function
  - 12.7.8 Sorting a List of Values
  - 12.7.9 Calling a Function
  - 12.7.10 Timing Functions and Commands
  - 12.7.11 Determining the Operating System
  - 12.7.12 Local Time CLIPS Basic Programming Guide vii
  - 12.7.13 Greenwich Mean Time
  - 12.7.14 Getting the Error State
  - 12.7.15 Clearing the Error State
  - 12.7.16 Setting the Error State
  - 12.7.17 Void Value
- 12.8 Deftemplate Functions
  - 12.8.1 Determining the Module in which a Deftemplate is Defined
  - 12.8.2 Getting the Allowed Values for a Deftemplate Slot
  - 12.8.3 Getting the Cardinality for a Deftemplate Slot
  - 12.8.4 Testing whether a Deftemplate Slot has a Default................................................
  - 12.8.5 Getting the Default Value for a Deftemplate Slot
  - 12.8.6 Deftemplate Slot Existence
  - 12.8.7 Testing whether a Deftemplate Slot is a Multifield Slot
  - 12.8.8 Determining the Slot Names Associated with a Deftemplate
  - 12.8.9 Getting the Numeric Range for a Deftemplate Slot
  - 12.8.10 Testing whether a Deftemplate Slot is a Single-Field Slot
  - 12.8.11 Getting the Primitive Types for a Deftemplate Slot
  - 12.8.12 Getting the List of Deftemplates
- 12.9 Fact Functions
  - 12.9.1 Creating New Facts
  - 12.9.2 Removing Facts from the Fact-list
  - 12.9.3 Modifying Template Facts
  - 12.9.4 Duplicating Template Facts
  - 12.9.5 Asserting a String
  - 12.9.6 Getting the Fact-Index of a Fact-address
  - 12.9.7 Determining If a Fact Exists
  - 12.9.8 Determining the Deftemplate (Relation) Name Associated with a Fact
  - 12.9.9 Determining the Slot Names Associated with a Fact............................................
  - 12.9.10 Retrieving the Slot Value of a Fact
  - 12.9.11 Retrieving the Fact-List
  - 12.9.12 Fact-set Queries and Distributed Actions
- 12.10 Deffacts Functions
  - 12.10.1 Getting the List of Deffacts.................................................................................
  - 12.10.2 Determining the Module in which a Deffacts is Defined
- 12.11 Defrule Functions.........................................................................................................
  - 12.11.1 Getting the List of Defrules
  - 12.11.2 Determining the Module in which a Defrule is Defined.....................................
- 12.12 Agenda Functions
  - 12.12.1 Getting the Current Focus
  - 12.12.2 Getting the Focus Stack
  - 12.12.3 Removing the Current Focus from the Focus Stack
- 12.13 Defglobal Functions
  - 12.13.1 Getting the List of Defglobals............................................................................. viii Table of Contents
  - 12.13.2 Determining the Module in which a Defglobal is Defined
- 12.14 Deffunction Functions
  - 12.14.1 Getting the List of Deffunctions
  - 12.14.2 Determining the Module in which a Deffunction is Defined
- 12.15 Generic Function Functions
  - 12.15.1 Getting the List of Defgenerics
  - 12.15.2 Determining the Module in which a Generic Function is Defined
  - 12.15.3 Getting the List of Defmethods...........................................................................
  - 12.15.4 Type Determination
  - 12.15.5 Existence of Shadowed Methods
  - 12.15.6 Calling Shadowed Methods
  - 12.15.7 Calling Shadowed Methods with Overrides
  - 12.15.8 Calling a Specific Method
  - 12.15.9 Getting the Restrictions of Defmethods
- 12.16 Defclass Functions
  - 12.16.1 Getting the List of Defclasses
  - 12.16.2 Determining the Module in which a Defclass is Defined
  - 12.16.3 Determining if a Class Exists
  - 12.16.4 Superclass Determination
  - 12.16.5 Subclass Determination
  - 12.16.6 Slot Existence......................................................................................................
  - 12.16.7 Testing whether a Slot is Writable
  - 12.16.8 Testing whether a Slot is Initializable
  - 12.16.9 Testing whether a Slot is Public..........................................................................
  - 12.16.10 Testing whether a Slot can be Accessed Directly
  - 12.16.11 Message-handler Existence
  - 12.16.12 Determining if a Class can have Direct Instances
  - 12.16.13 Determining if a Class can Satisfy Object Patterns
  - 12.16.14 Getting the List of Superclasses for a Class......................................................
  - 12.16.15 Getting the List of Subclasses for a Class
  - 12.16.16 Getting the List of Slots for a Class
  - 12.16.17 Getting the List of Message-Handlers for a Class
  - 12.16.18 Getting the List of Facets for a Slot
  - 12.16.19 Getting the List of Source Classes for a Slot
  - 12.16.20 Getting the Primitive Types for a Slot
  - 12.16.21 Getting the Cardinality for a Slot
  - 12.16.22 Getting the Allowed Values for a Slot
  - 12.16.23 Getting the Numeric Range for a Slot...............................................................
  - 12.16.24 Getting the Default Value for a Slot
  - 12.16.25 Setting the Defaults Mode for Classes
  - 12.16.26 Getting the Defaults Mode for Classes
  - 12.16.27 Getting the Allowed Classes for a Slot
  - 12.17 Message-handler Functions CLIPS Basic Programming Guide ix
    - 12.17.1 Existence of Shadowed Handlers........................................................................
    - 12.17.2 Calling Shadowed Handlers
    - 12.17.3 Calling Shadowed Handlers with Different Arguments
  - 12.18 Definstances Functions
    - 12.18.1 Getting the List of Definstances
    - 12.18.2 Determining the Module in which a Definstances is Defined
  - 12.19 Instance Functions
    - 12.19.1 Initializing an Instance
    - 12.19.2 Deleting an Instance
    - 12.19.3 Deleting the Active Instance from a Handler
    - 12.19.4 Determining the Class of an Object
    - 12.19.5 Determining the Name of an Instance
    - 12.19.6 Determining the Address of an Instance
    - 12.19.7 Converting a Symbol to an Instance-Name
    - 12.19.8 Converting an Instance-Name to a Symbol
    - 12.19.9 Testing for an Instance
    - 12.19.10 Testing for an Instance-Address
    - 12.19.11 Testing for an Instance-Name
    - 12.19.12 Testing for the Existence an Instance
    - 12.19.13 Reading a Slot Value
    - 12.19.14 Setting a Slot Value
    - 12.19.15 Replacing Fields in a Slot
    - 12.19.16 Inserting Fields in a Slot
    - 12.19.17 Deleting Fields in a Slot
  - 12.20 Defmodule Functions
    - 12.20.1 Getting the List of Defmodules...........................................................................
    - 12.20.2 Setting the Current Module
    - 12.20.3 Getting the Current Module
  - 12.21 Sequence Expansion
    - 12.21.1 Sequence Expansion and Rules
    - 12.21.2 Multifield Expansion Function
    - 12.21.3 Setting The Sequence Operator Recognition Behavior
    - 12.21.4 Getting The Sequence Operator Recognition Behavior......................................
    - 12.21.5 Sequence Operator Caveat
- Section 13: Commands
  - 13.1 Environment Commands
    - 13.1.1 Loading Constructs From A File
    - 13.1.2 Loading Constructs From A File without Progress Information
    - 13.1.3 Saving All Constructs To A File
    - 13.1.4 Loading a Binary Image........................................................................................
    - 13.1.5 Saving a Binary Image
  - 13.1.6 Clearing CLIPS x Table of Contents
  - 13.1.7 Exiting CLIPS
  - 13.1.8 Resetting CLIPS....................................................................................................
  - 13.1.9 Executing Commands From a File
  - 13.1.10 Executing Commands From a File Without Replacing Standard Input
  - 13.1.11 Determining CLIPS Compilation Options
  - 13.1.12 Calling the Operating System
  - 13.1.13 Setting the Dynamic Constraint Checking Behavior
  - 13.1.14 Getting the Dynamic Constraint Checking Behavior
  - 13.1.15 Finding Symbols
- 13.2 Debugging Commands...................................................................................................
  - 13.2.1 Generating Trace Files
  - 13.2.2 Closing Trace Files
  - 13.2.3 Enabling Watch Items
  - 13.2.4 Disabling Watch Items
  - 13.2.5 Viewing the Current State of Watch Items
- 13.3 Deftemplate Commands.................................................................................................
  - 13.3.1 Displaying the Text of a Deftemplate
  - 13.3.2 Displaying the List of Deftemplates
  - 13.3.3 Deleting a Deftemplate
- 13.4 Fact Commands
  - 13.4.1 Displaying the Fact-List
  - 13.4.2 Displaying a Single Fact
  - 13.4.3 Saving Facts To A Text File
  - 13.4.4 Saving Facts to a Binary File
  - 13.4.5 Loading Facts From a Text File
  - 13.4.6 Loading Facts from a Binary File
  - 13.4.7 Setting the Duplication Behavior of Facts
  - 13.4.8 Getting the Duplication Behavior of Facts
- 13.5 Deffacts Commands
  - 13.5.1 Displaying the Text of a Deffacts
  - 13.5.2 Displaying the List of Deffacts
  - 13.5.3 Deleting a Deffacts
- 13.6 Defrule Commands
  - 13.6.1 Displaying the Text of a Rule
  - 13.6.2 Displaying the List of Rules
  - 13.6.3 Deleting a Defrule
  - 13.6.4 Displaying Matches for a Rule
  - 13.6.5 Setting a Breakpoint for a Rule
  - 13.6.6 Removing a Breakpoint for a Rule
  - 13.6.7 Displaying Rule Breakpoints
  - 13.6.8 Refreshing a Rule
  - 13.6.9 Determining the Logical Dependencies of a Pattern Entity..................................
  - 13.6.10 Determining the Logical Dependents of a Pattern Entity CLIPS Basic Programming Guide xi
- 13.7 Agenda Commands
  - 13.7.1 Displaying the Agenda
  - 13.7.2 Running CLIPS
  - 13.7.3 Focusing on a Group of Rules
  - 13.7.4 Stopping Rule Execution
  - 13.7.5 Setting The Current Conflict Resolution Strategy
  - 13.7.6 Getting The Current Conflict Resolution Strategy
  - 13.7.7 Listing the Module Names on the Focus Stack
  - 13.7.8 Removing all Module Names from the Focus Stack
  - 13.7.9 Setting the Salience Evaluation Behavior
  - 13.7.10 Getting the Salience Evaluation Behavior
  - 13.7.11 Refreshing the Salience Value of Rules on the Agenda
- 13.8 Defglobal Commands
  - 13.8.1 Displaying the Text of a Defglobal
  - 13.8.2 Displaying the List of Defglobals
  - 13.8.3 Deleting a Defglobal
  - 13.8.4 Displaying the Values of Global Variables
  - 13.8.5 Setting the Reset Behavior of Global Variables
  - 13.8.6 Getting the Reset Behavior of Global Variables...................................................
- 13.9 Deffunction Commands
  - 13.9.1 Displaying the Text of a Deffunction
  - 13.9.2 Displaying the List of Deffunctions
  - 13.9.3 Deleting a Deffunction
- 13.10 Generic Function Commands
  - 13.10.1 Displaying the Text of a Generic Function Header
  - 13.10.2 Displaying the Text of a Generic Function Method
  - 13.10.3 Displaying the List of Generic Functions
  - 13.10.4 Displaying the List of Methods for a Generic Function
  - 13.10.5 Deleting a Generic Function
  - 13.10.6 Deleting a Generic Function Method
  - 13.10.7 Previewing a Generic Function Call
- 13.11 Defclass Commands.....................................................................................................
  - 13.11.1 Displaying the Text of a Defclass
  - 13.11.2 Displaying the List of Defclasses
  - 13.11.3 Deleting a Defclass
  - 13.11.4 Examining a Class...............................................................................................
  - 13.11.5 Examining the Class Hierarchy
- 13.12 Message-handler Commands
  - 13.12.1 Displaying the Text of a Defmessage-handler
  - 13.12.2 Displaying the List of Defmessage-handlers
  - 13.12.3 Deleting a Defmessage-handler
  - 13.12.4 Previewing a Message.........................................................................................
  - 13.13 Definstances Commands xii Table of Contents
    - 13.13.1 Displaying the Text of a Definstances
    - 13.13.3 Deleting a Definstances
  - 13.14 Instances Commands
    - 13.14.1 Listing the Instances
    - 13.14.2 Printing an Instance’s Slots from a Handler
    - 13.14.3 Saving Instances to a Text File
    - 13.14.4 Saving Instances to a Binary File........................................................................
    - 13.14.5 Loading Instances from a Text File
    - 13.14.6 Loading Instances from a Text File without Message Passing
    - 13.14.7 Loading Instances from a Binary File
  - 13.15 Defmodule Commands
    - 13.15.1 Displaying the Text of a Defmodule
    - 13.15.2 Displaying the List of Defmodules
  - 13.16 Memory Management Commands
    - 13.16.1 Determining the Amount of Memory Used by CLIPS
    - 13.16.2 Determining the Number of Memory Requests Made by CLIPS
    - 13.16.3 Releasing Memory Used by CLIPS
    - 13.16.4 Conserving Memory
  - 13.17 External Text Manipulation
    - 13.17.1 External Text File Format
    - 13.17.2 Loading External Text
    - 13.17.3 Printing External Text
    - 13.17.4 Retrieving External Text
    - 13.17.5 Unloading an External Text File
  - 13.18 Profiling Commands
    - 13.18.1 Setting the Profiling Report Threshold
    - 13.18.2 Getting the Profiling Report Threshold
    - 13.18.3 Resetting Profiling Information
    - 13.18.4 Displaying Profiling Information
    - 13.18.5 Profiling Constructs and User Functions
- Appendix A: Support Information
  - A.1 Questions and Information
  - A.2 Documentation
  - A.3 CLIPS Source Code and Executables
- Appendix B: Update Release Notes
- Appendix C: Glossary...............................................................................................................
- Appendix D: Performance Considerations
  - D.1 Ordering of Patterns on the LHS.....................................................................................
  - D.2 Deffunctions versus Generic Functions
  - D.3 Ordering of Method Parameter Restrictions CLIPS Basic Programming Guide xiii
  - D.4 Instance-Addresses versus Instance-Names....................................................................
  - D.5 Reading Instance Slots Directly
- Appendix E: CLIPS Warning Messages
- Appendix F: CLIPS Error Messages
- Appendix G: CLIPS BNF
- Appendix H: Reserved Function Names
- Index

```
xiv Table of Contents
```

## License Information

MIT No Attribution

Copyright 2023 Secret Society Software, LLC

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and
associated documentation files (the "Software"), to deal in the Software without restriction,
including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense,
and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do
so.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED,
INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A
PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN
AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

```
CLIPS Basic Programming Guide xv
```

## Preface

About CLIPS

Developed at NASA’s Johnson Space Center from 1985 to 1996, the ‘C’ Language Integrated
Production System (CLIPS) is a rule-based programming language useful for creating expert
systems and other programs where a heuristic solution is easier to implement and maintain than an
algorithmic solution. Written in C for portability, CLIPS can be installed and used on a wide
variety of platforms. Since 1996, CLIPS has been available as public domain software.

CLIPS Version 6. 4

Version 6.4 of CLIPS includes three major enhancements: a redesigned C Application
Programming Interface (API); wrapper classes and example programs for .NET and Java; and
Integrated Development Environments (IDEs) with Unicode support for Windows and Java. For a
detailed listing of differences between releases of CLIPS, refer to appendix B of the Basic
Programming Guide and appendix B of the Advanced Programming Guide.

CLIPS Documentation

```
Two documents are provided with CLIPS.
```

- The CLIPS Reference Manual which is split into several volumes:
  - Volume I - The Basic Programming Guide documents the CLIPS programming language.
  - Volume II - The Advanced Programming Guide documents the C Application
    Programming Interfaces for embedding and extending CLIPS.
  - Volume III - The Interfaces Guide documents the CLIPS Integrated Development
    Environments, wrapper classes, and example programs.
- The _CLIPS User’s Guide_ provides an introduction to CLIPS and rule-based programming.

```
xvi Preface
```

Other Documentation

```
Adventures in Rule-Based Programming is a fun
introduction to writing applications using CLIPS. In this
tutorial you’ll learn the basic concepts of rule-based
programming, where rules are used to specify the logic of
what must be accomplished, but an inference engine
determines when rules are applied. You’ll incrementally
create a fully functional text adventure game, and in the
process, learn how to write, organize, debug, test, and
deploy CLIPS code. Visit clipsrules.net/airbp for more
information.
```

```
CLIPS Basic Programming Guide 1
```

## Section 1:

## Introduction

The Basic Programming Guide documents the syntax, features, and behavior of the CLIPS
programming language. No previous expert system background is required, although a general
understanding of computer languages is assumed. Section 2 of this manual provides an overview
of the CLIPS language and basic terminology. Sections 3 through 11 provide additional details
regarding the CLIPS programming language on topics such as rules and the CLIPS Object
Oriented Programming Language (COOL). The types of actions and functions provided by CLIPS
are defined in section 12. Finally, commands typically used from the CLIPS interactive interface
are described in section 13.

```
2 Section 2: CLIPS Overview
```

## Section 2: CLIPS Overview...........................................................................................................

This section gives a general overview of CLIPS and of the basic concepts used throughout this
manual.

### 2.1 Interacting with CLIPS

CLIPS programs may be executed in three ways: interactively using a simple Read-Eval-Print
Loop (REPL) interface; interactively using an Integrated Development Environment (IDE)
interface; or as embedded application in which the user provides a main program and controls
execution of the expert system through the CLIPS Application Programming Interface (API).

The CLIPS REPL interface is similar to a LISP or Python REPL and is portable to all
environments. Standard usage for the REPL is to create or edit a knowledge base using any
standard text editor; save the knowledge base as one or more text files; then load, debug, and run
the knowledge base using the CLIPS REPL.

Integrated Development Environments are also available for macOS, Windows, and Java. The
IDEs provide an enhanced REPL that supports inline editing and a command history; dialog boxes
for specifying files and directories; and debugging windows for displaying the current state of a
CLIPS program. The IDEs are described in more detail in the Interfaces Guide.

Embedded applications are discussed in the Advanced Programming Guide.

#### 2.1.1 Read-Eval-Print Loop

The primary method for interacting with CLIPS in a non-embedded environment is through the
CLIPS Read-Eval-Print Loop (REPL). When the “CLIPS>” prompt is displayed, CLIPS will wait
for input to evaluate. Once valid input is provided and followed by pressing the return key, the
input will be evaluated and the result (if any) will be printed. Any extraneous input following the
valid input is then discarded. Valid input is a function call, construct, local or global variable, or
constant. Function calls in CLIPS use a prefix notation—the operands to a function always appear
after the function name. Entering a construct definition at the CLIPS prompt creates a new
construct of the appropriate type. Both function calls and constructs use parentheses as delimiters
and these must be properly balanced, otherwise the input will not be evaluated or an error will
occur. Entering a global variable causes the value of the global variable to be printed. Local
variables can be set at the command prompt using the bind function and retain their value until a
reset or clear command is issued. Entering a local variable causes the value of the local variable to

```
CLIPS Basic Programming Guide 3
```

be printed. Entering a constant causes the constant to be printed (which is not very useful).
Example interaction with the REPL is shown following.

```
CLIPS (6.4.1 4/8/23)
CLIPS> (+ 3 4)
7
CLIPS> (defglobal ?*x* = 3)
CLIPS> ?*x*
3
CLIPS> red
red
CLIPS> (bind ?a 5)
5
CLIPS> (+ ?a 3)
8
CLIPS> (reset)
CLIPS> ?a
[EVALUATN1] Variable a is unbound
FALSE
CLIPS>
```

First the addition function is called adding the numbers 3 and 4 to yield the result 7. A global
variable ?_x_ is then defined and given the value 3. The variable ?_x_ is then entered at the prompt
and its value is returned. The constant symbol red is entered and returned (since a constant
evaluates to itself). The local variable ?a is assigned the value 5 using the bind function. The
addition function is called to add the variable ?a to the integer 3 yielding 8. The reset command is
called to reset the CLIPS environment (which among other effects removes the assignment of local
variables). When the variable ?a is entered at the prompt, an error occurs because the variable is
no longer bound.

#### 2.1.2 Automated Command Entry and Loading

Some operating systems allow additional arguments to be specified to a program when it begins
execution. When the CLIPS executable is started under such an operating system, CLIPS can be
made to automatically execute a series of commands read directly from a file or to load constructs
from a file. The command-line syntax for starting CLIPS and automatically reading commands or
loading constructs from a file is shown following.

Syntax

```
clips <option>*
```

```
<option> ::= -f <filename> |
```

- f2 <filename> |
- l <filename>

For the -f option, <filename> is a file that contains CLIPS commands. If the exit command is
included in the file, CLIPS will halt and the user is returned to the operating system after executing

```
4 Section 2: CLIPS Overview
```

the commands in the file. If an exit command is not in the file, CLIPS will enter in its interactive
state after executing the commands in the file. Commands in the file should be entered exactly as
they would be interactively (i.e. opening and closing parentheses must be included and a carriage
return must be at the end of the command). The -f command line option is equivalent to
interactively entering a batch command as the first command to the CLIPS prompt.

The -f2 option is similar to the -f option, but is equivalent to interactively entering a batch\*
command. The commands stored in <filename> are immediately executed, but the commands and
their return values are not displayed as they would be for a batch command.

For the -l option, <filename> should be a file containing CLIPS constructs. This file will be loaded
into the environment. The -l command line option is equivalent to interactively entering a load
command.

Files specified using the **–** f option are not processed until the CLIPS prompt appears, so these files
will always be processed after files specified using the **–** f2 and **–** l options.

### 2.2 Reference Manual Syntax

Terminology is used throughout this manual to describe the syntax of CLIPS constructs and
functions. Plain words or characters (including parentheses) are to be typed exactly as they appear.
Sequences of words enclosed in single-angle brackets (called terms or non-terminal symbols), such
as <string>, represent a single entity of the named class of items to be supplied by the user. A
non-terminal symbol followed by a _, represents zero or more entities of the named class of items.
A non-terminal symbol followed by a +, represents one or more entities of the named class of
items. A _ or + by itself is to be typed as it appears. Vertical and horizontal ellipsis (three dots
arranged respectively vertically and horizontally) are also used between non-terminal symbols to
indicate the occurrence of one or more entities. A term enclosed within square brackets, such as
[<comment>], is optional (i.e. it may or may not be included). Vertical bars indicate a choice
between multiple terms. White spaces (tabs, spaces, carriage returns) are used by CLIPS only as
delimiters between terms and are ignored otherwise (unless inside double quotes). The ::= symbol
is used to indicate how a non-terminal symbol can be replaced. For example, the following syntax
description indicates that a <lexeme> can be replaced with either a <symbol> or a <string>.

```
<lexeme> ::= <symbol> | <string>
```

A complete BNF listing for CLIPS constructs along with some commonly used replacements for
non-terminal symbols are listed in appendix G.

```
CLIPS Basic Programming Guide 5
```

### 2.3 Basic Programming Elements

CLIPS provides three basic elements for writing programs: primitive data types, functions for
manipulating data, and constructs for adding to a knowledge base.

#### 2.3.1 Data Types

CLIPS provides eight primitive data types for representing information. These types are float,
integer, symbol, string, external-address, fact-address, instance-name and instance-address.
Numeric information can be represented using floats and integers. Symbolic information can be
represented using symbols and strings.

A number consists only of digits (0-9), a decimal point (.), a sign (+ or -), and, optionally, an (e)
for exponential notation with its corresponding sign. A number is either stored as a float or an
integer. Any number consisting of an optional sign followed by only digits is stored as an integer
(represented internally by CLIPS as a C long long integer). All other numbers are stored as floats
(represented internally by CLIPS as a C double-precision float). The number of significant digits
will depend on the machine implementation. Roundoff errors also may occur, again depending on
the machine implementation. As with any computer language, care should be taken when
comparing floating-point values to each other or comparing integers to floating-point values. Some
examples of integers are

```
237 15 +12 - 32
```

Some examples of floats are

```
237e3 15.09 +12.0 -32.3e- 7
```

Specifically, integers use the following format:

```
<integer> ::= [+ | -] <digit>+
```

```
<digit> ::= 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9
```

Floating point numbers use the following format:

```
<float> ::= <integer> <exponent> |
```

```
<integer>. [<exponent>] |
```

. <unsigned integer> [<exponent>] |

```
<integer>. <unsigned integer> [<exponent>]
```

```
<unsigned-integer> ::= <digit>+
```

```
6 Section 2: CLIPS Overview
```

```
<exponent> ::= e | E <integer>
```

A sequence of characters which does not exactly follow the format of a number is treated as a
symbol.

A symbol in CLIPS is any sequence of characters that starts with any printable ASCII character
and is followed by zero or more printable ASCII characters. When a delimiter is found, the symbol
is ended. The following characters act as delimiters: any non-printable ASCII character (including
spaces, tabs, carriage returns, and line feeds), a double quote, opening and closing parentheses “(”
and “)”, an ampersand “&”, a vertical bar “|”, a less than “<”, and a tilde “~”. A semicolon “;”
starts a CLIPS comment and also acts as a delimiter. Delimiters may not be included in symbols
with the exception of the “<“ character which may be the first character in a symbol. In addition,
a symbol may not begin with either the “?” character or the “$?” sequence of characters (although
a symbol may contain these characters). These characters are reserved for variables. CLIPS is case
sensitive (i.e. uppercase letters will match only uppercase letters). Note that numbers are a special
case of symbols (i.e. they satisfy the definition of a symbol, but they are treated as a different data
type). Some simple examples of symbols are

```
red Hello B76-HI bad_value
```

```
127A 456- 93 - 039 @+=-% 2each
```

A string is a set of characters that starts with a double quote (") and is followed by zero or more
printable characters. A string ends with double quotes. Double quotes may be embedded within a
string by placing a backslash (\) in front of the character. A backslash may be embedded by placing
two consecutive backslash characters in the string. Some examples are

```
"red" "a and b" "1 number" "a\"quote"
```

Note that the string “abcd" is not the same as the symbol abcd. They both contain the same
characters, but are of different types. The same holds true for the instance name [abcd].

An external-address is the address of an external data structure returned by a function (written in
a language such as C or Java) that has been integrated with CLIPS. This data type can only be
created by calling a function (i.e. it is not possible to specify an external-address using text). In the
basic version of CLIPS (which has no user defined external functions), it is not possible to create
this data type. External-addresses are discussed in further detail in the Advanced Programming
Guide. Within CLIPS, the printed representation of an external-address is

```
<Pointer-C-XXXXXX>
```

where XXXXXX is the external-address.

```
CLIPS Basic Programming Guide 7
```

A fact is a list of primitive values that are either referenced positionally (ordered facts) or by name
(non-ordered or template facts). Facts are referred to by index or fact-address. The printed format
of a fact-address is:

```
<Fact-XXX>
```

where XXX is the fact-index.

An instance is an object that is an instantiation or specific example of a class. Objects in CLIPS
are defined to be floats, integers, symbols, strings, multifield values, external-addresses,
fact-addresses, and instances of a user-defined class. A user-defined class is created using the
defclass construct. An instance of a user-defined class is created with the make-instance function,
and such an instance can be referred to uniquely by address. An instance-name is formed by
enclosing a symbol within left and right brackets. Thus, pure symbols may not be surrounded by
brackets. If the CLIPS Object Oriented Language (COOL) is not included in a particular CLIPS
configuration, then brackets may be wrapped around symbols. Some examples of instance-names
are:

```
[pump-1] [red] [+++] [123-890]
```

Note that the brackets are not part of the name of the instance; they merely indicate that the
enclosed symbol is an instance-name. An instance-address can only be obtained by binding the
return value of a function called instance-address or by binding a variable to an instance matching
an object pattern on the LHS of a rule (i.e., it is not possible to specify an instance-address by
typing the value). A reference to an instance of a user-defined class can either be by name or
address. Within CLIPS, the printed representation of an instance-address is

```
<Instance-XXX>
```

where XXX is the name of the instance.

In CLIPS, a placeholder that has a value (one of the primitive data types) is referred to as a field.
The primitive data types are referred to as single-field values. A constant is a non-varying single-
field value directly expressed as a series of characters (which means that external-addresses,
fact-addresses and instance-addresses cannot be expressed as constants because they can only be
obtained through function calls and variable bindings). A multifield value is a sequence of zero
or more single-field values. When displayed by CLIPS, multifield values are enclosed in
parentheses. Collectively, single and multifield values are referred to as values. Some examples
of multifield values are

```
(a) (1 blue red) () (x 3.0 "red" 567)
```

Note that the multifield value (a) is not the same as the single field value a. Multifield values are
created either by calling functions which return multifield values, by using wildcard arguments in

```
8 Section 2: CLIPS Overview
```

a deffunction, object message-handler, or method, or by binding variables during the
pattern-matching process for rules. In CLIPS, a variable is a symbolic location that is used to store
values. Variables are used by many of the CLIPS constructs (such as defrule, deffunction,
defmethod, and defmessage-handler) and their usage is explained in the sections describing each
of these constructs.

#### 2.3.2 Functions

A function in CLIPS is a piece of executable code identified by a specific name which returns a
useful value or performs a useful side effect (such as displaying information). Throughout the
CLIPS documentation, the word function is generally used to refer only to functions which return
a value (whereas commands and actions are used to refer to functions which have a side effect but
generally do not return a value).

There are several types of functions. User defined functions and system defined functions are
pieces of code that have been written in an external language (such as C, Java, or C#) and linked
with the CLIPS environment. System defined functions are those functions that have been defined
internally by the CLIPS environment. User defined functions are functions that have been defined
externally of the CLIPS environment. A complete list of system defined functions can be found in
appendix H.

The deffunction construct allows users to define new functions directly in the CLIPS environment
using CLIPS syntax. Functions defined in this manner appear and act like other functions,
however, instead of being directly executed (as code written in an external language would be)
they are interpreted by the CLIPS environment.

Generic functions can be defined using the defgeneric and defmethod constructs. Generic
functions allow different pieces of code to be executed depending upon the arguments passed to
the generic function. Thus, a single function name can be overloaded with more than one piece of
code.

Function calls in CLIPS use a prefix notation – the arguments to a function always appear after
the function name. Function calls begin with a left parenthesis, followed by the name of the
function, then the arguments to the function follow (each argument separated by one or more
spaces). Arguments to a function can be primitive data types, variables, or another function call.
The function call is then closed with a right parenthesis.

```
CLIPS Basic Programming Guide 9
```

Example

```
CLIPS> (+ 3 4 5)
12
CLIPS> (* 5 6.0 2)
60.0
CLIPS> (+ 3 (* 8 9) 4)
79
CLIPS> (* 8 (+ 3 (* 2 3 4) 9) (* 3 4))
3456
CLIPS>
```

While a function refers to a piece of executable code identified by a specific name, an expression
refers to a function which has its arguments specified (which may or may not be functions calls as
well). Thus the previous example contains expressions which make calls to the \* and + functions.

#### 2.3.3 Constructs

Several defining constructs appear in CLIPS: defmodule, defrule, deffacts, deftemplate,
defglobal, deffunction, defclass, definstances, defmessage-handler, defgeneric, and
defmethod. All constructs in CLIPS are surrounded by parentheses. The construct opens with a
left parenthesis and closes with a right parenthesis. Defining a construct differs from calling a
function primarily in effect. Typically a function call leaves the CLIPS environment unchanged
(with some notable exceptions such as resetting or clearing the environment or opening a file).
Defining a construct, however, is explicitly intended to alter the CLIPS environment by adding to
the CLIPS knowledge base. Unlike function calls, constructs never have a return value.

As with any programming language, it is highly beneficial to comment CLIPS code. All constructs
(with the exception of defglobal) allow a comment directly following the construct name.
Comments also can be placed within CLIPS code by using a semicolon (;). Everything from the
semicolon until the next return character will be ignored by CLIPS. If the semicolon is the first
character in the line, the entire line will be treated as a comment. Semicolon commented text is not
saved by CLIPS when loading constructs (however, the optional comment string within a construct
is saved).

### 2.4 Data Abstraction

There are three primary formats for representing information in CLIPS: facts, objects and global
variables.

```
10 Section 2: CLIPS Overview
```

#### 2.4.1 Facts

Facts are one of the basic high-level forms for representing information in a CLIPS system. Each
fact represents a piece of information that has been placed in the current list of facts, called the
fact-list. Facts are the fundamental unit of data used by rules.

Facts may be added to the fact-list (using the assert command), removed from the fact-list (using
the retract command), modified (using the modify command), or duplicated (using the duplicate
command) through explicit user interaction or as a CLIPS program executes. If a fact is asserted
into the fact-list that exactly matches an already existing fact, the new assertion will be ignored
(however, this behavior can be changed using the set-fact-duplication function).

Some commands, such as the retract, modify, and duplicate commands, require a fact to be
specified. A fact can be specified either by fact-index or fact-address. Whenever a fact is asserted
it is given a unique integer index called a fact-index. Fact-indices start at one and are incremented
by one for each new fact. When a fact is modified, its fact-index remains unchanged. Whenever a
reset or clear command is given, the fact-indices restart at one. A fact may also be specified
through the use of a fact-address. A fact-address can be obtained by capturing the return value of
commands which return fact addresses (such as assert, modify, and duplicate) or by binding a
variable to the fact address of a fact which matches a pattern on the LHS of a rule.

A fact identifier is a shorthand notation for displaying a fact. It consists of the character “f”,
followed by a dash, followed by the fact-index of the fact. For example, f-10 refers to the fact with
fact-index 10.

A fact is stored in one of two formats: ordered or non-ordered.

2.4.1.1 Ordered Facts

Ordered facts consist of a symbol followed by a sequence of zero or more fields separated by
spaces and delimited by an opening parenthesis on the left and a closing parenthesis on the right.
The first field of an ordered fact specifies a “relation” that applies to the remaining fields in the
ordered fact. For example, (father-of jack bill) states that bill is the father of jack.

Some examples of ordered facts are shown following.

```
(the pump is on)
(altitude is 10000 feet)
(grocery-list bread milk eggs)
```

Fields in a non-ordered fact may be of any of the primitive data types (with the exception of the
first field which must be a symbol), and no restriction is placed on the ordering of fields. The
following symbols are reserved and should not be used as the first field in any fact (ordered or

```
CLIPS Basic Programming Guide 11
```

non-ordered): test, and, or, not, declare, logical, object, exists, and forall. These words are reserved
only when used as a deftemplate name (whether explicitly defined or implied). These symbols may
be used as slot names, however, this is not recommended.

2.4.1.2 Non-ordered Facts

Ordered facts encode information positionally. To access that information, a user must know not
only what data is stored in a fact but which position contains the data. Non-ordered (or
deftemplate) facts provide the user with the ability to abstract the structure of a fact by assigning
names to each field in the fact. The deftemplate construct is used to create a template that can then
be used to access fields by name. The deftemplate construct is analogous to a structure definition
in C.

The deftemplate construct allows the name of a template to be defined along with zero or more
definitions of slots. Unlike ordered facts, the slots of a deftemplate fact may be constrained by
type, value, and numeric range. In addition, default values can be specified for a slot. A slot
consists of an opening parenthesis followed by the name of the slot, zero or more fields, and a
closing parenthesis. Note that slots may not be used in an ordered fact and that information in a
deftemplate fact may not be referenced positionally.

Deftemplate facts are distinguished from ordered facts by the first field within the fact. The first
field of all facts must be a symbol, however, if that symbol corresponds to the name of a
deftemplate, then the fact is a deftemplate fact. The first field of a deftemplate fact is followed by
a list of zero or more slots. As with ordered facts, deftemplate facts are enclosed by an opening
parenthesis on the left and a closing parenthesis on the right.

Some examples of deftemplate facts are shown following.

```
(client (name "Joe Brown") (id X9345A))
(point-mass (x-velocity 100) (y-velocity -200))
(class (teacher "Martha Jones") (#-students 30) (Room "37A"))
(grocery-list (#-of-items 3) (items bread milk eggs))
```

Note that the order of slots in a deftemplate fact is not important. For example the following facts
are all identical:

```
(class (teacher "Martha Jones") (#-students 30) (Room "37A"))
(class (#-students 30) (teacher "Martha Jones") (Room "37A"))
(class (Room "37A") (#-students 30) (teacher "Martha Jones"))
```

In contrast, note that the following ordered fact are not identical.

```
(class "Martha Jones" 30 "37A")
(class 30 "Martha Jones" "37A")
(class "37A" 30 "Martha Jones")
```

```
12 Section 2: CLIPS Overview
```

In addition to being asserted and retracted, deftemplate facts can also be modified and duplicated
(using the modify and duplicate commands). Modifying a fact changes a set of specified slots
within that fact. Duplicating a fact creates a new fact identical to the original fact and then changes
a set of specified slots within the new fact. The benefit of using the modify and duplicate
commands is that slots which don’t change, don’t have to be specified.

2.4.1.3 Initial Facts

The deffacts construct allows a set of a priori or initial knowledge to be specified as a collection
of facts. When the CLIPS environment is reset (using the reset command) every fact specified
within a deffacts construct in the CLIPS knowledge base is added to the fact-list.

#### 2.4.2 Objects

An object in CLIPS is defined to be a symbol, a string, a floating-point or integer number, a
multifield value, an external-address, or an instance of a user-defined class. Objects are described
in two basic parts: properties and behavior. A class is a template for common properties and
behavior of objects that are instances of that class. Some examples of objects and their classes are:

```
Object (Printed Representation) Class
```

Rolls-Royce (^) SYMBOL
"Rolls-Royce" (^) STRING
8.0 (^) FLOAT
(^8) INTEGER
(8.0 Rolls-Royce 8 [Rolls-Royce]) (^) MULTIFIELD
<Pointer-00CF61AB> (^) EXTERNAL-ADDRESS
[Rolls-Royce] (^) CAR (a user-defined class)
Objects in CLIPS are split into two important categories: primitive types and instances of
user-defined classes. These two types of objects differ in the way they are referenced, created and
deleted as well as how their properties are specified.
Primitive type objects are referenced simply by giving their value, and they are created and deleted
implicitly by CLIPS as they are needed. Primitive type objects have no names or slots, and their
classes are predefined by CLIPS. The behavior of primitive type objects is like that of instances of
user-defined classes, however, in that you can define message-handlers and attach them to the
primitive type classes. It is anticipated that primitive types will not be used often in an
object-oriented programming (OOP) context; the main reason classes are provided for them is for

```
CLIPS Basic Programming Guide 13
```

use in generic functions. Generic functions use the classes of their arguments to determine which
methods to execute.

An instance of a user-defined class is referenced by name or address, and they are created and
deleted explicitly via messages and special functions. The properties of an instance of a
user-defined class are expressed by a set of slots, which the object obtains from its class. As
previously defined, slots are named single field or multifield values. For example, the object
Rolls-Royce is an instance of the class CAR. One of the slots in class CAR might be “price”, and
the Rolls-Royce object’s value for this slot might be $75,000.00. The behavior of an object is
specified in terms of procedural code called message-handlers, which are attached to the object’s
class. All instances of a user-defined class have the same set of slots, but each instance may have
different values for those slots. However, two instances that have the same set of slots do not
necessarily belong to the same class, since two different classes can have identical sets of slots.

The primary difference between object slots and template (or non-ordered) facts is the notion of
inheritance. Inheritance allows the properties and behavior of a class to be described in terms of
other classes. COOL supports multiple inheritance: a class may directly inherit slots and
message-handlers from more than one class. Since inheritance is only useful for slots and
message-handlers, it is often not meaningful to inherit from one of the primitive type classes, such
as MULTIFIELD or NUMBER. This is because these classes cannot have slots and usually do not
have message-handlers.

2.4.2.1 Initial Objects

The definstances construct allows a set of a priori or initial knowledge to be specified as a
collection of instances of user-defined classes. When the CLIPS environment is reset (using the
reset command) every instance specified within a definstances construct in the CLIPS knowledge
base is added to the instance-list.

#### 2.4.3 Global Variables

The defglobal construct allows variables to be defined which are global in scope throughout the
CLIPS environment. That is, a global variable can be accessed anywhere in the CLIPS
environment and retains its value independent of other constructs. In contrast, some constructs
(such as defrule and deffunction) allow local variables to be defined within the definition of the
construct. These local variables can be referred to within the construct, but have no meaning
outside the construct. A CLIPS global variable is similar to global variables found in procedural
programming languages such as C and Java.

```
14 Section 2: CLIPS Overview
```

### 2.5 Knowledge Representation

CLIPS provides heuristic and procedural paradigms for representing knowledge. These two
paradigms are discussed in this section. Object-oriented programming (which combines aspects of
both data abstraction and procedural knowledge) is discussed in section 2.6.

#### 2.5.1 Heuristic Knowledge – Rules

One of the primary methods of representing knowledge in CLIPS is a rule. Rules are used to
represent heuristics, or “rules of thumb”, which specify a set of actions to be performed for a given
situation. The developer of an expert system defines a set of rules that collectively work together
to solve a problem. A rule is composed of an antecedent and a consequent. The antecedent of a
rule is also referred to as the if portion or the left-hand side (LHS) of the rule. The consequent of
a rule is also referred to as the then portion or the right-hand side (RHS) of the rule.

The antecedent of a rule is a set of conditions (or conditional elements) that must be satisfied for
the rule to be applicable. In CLIPS, the conditions of a rule are satisfied based on the existence or
non-existence of specified facts in the fact-list or specified instances of user-defined classes in the
instance-list. One type of condition that can be specified is a pattern. Patterns consist of a set of
restrictions that are used to determine which facts or objects satisfy the condition specified by the
pattern. The process of matching facts and objects to patterns is called pattern-matching. CLIPS
provides a mechanism, called the inference engine, which automatically matches patterns against
the current state of the fact-list and instance-list and determines which rules are applicable.

The consequent of a rule is the set of actions to be executed when the rule is applicable. The actions
of applicable rules are executed when the CLIPS inference engine is instructed to begin execution
of applicable rules. If more than one rule is applicable, the inference engine uses a conflict
resolution strategy to select which rule should have its actions executed. The actions of the
selected rule are executed (which may affect the list of applicable rules) and then the inference
engine selects another rule and executes its actions. This process continues until no applicable
rules remain.

In many ways, rules can be thought of as IF-THEN statements found in procedural programming
languages such as C and Java. However, the conditions of an IF-THEN statement in a procedural
language are only evaluated when the program flow of control is directly at the IF-THEN
statement. In contrast, rules act like WHENEVER-THEN statements. The inference engine always
keeps track of rules that have their conditions satisfied and thus rules can immediately be executed
when they are applicable. In this sense, rules are similar to exception handlers found in languages
such as Java.

```
CLIPS Basic Programming Guide 15
```

#### 2.5.2 Procedural Knowledge

CLIPS also supports a procedural paradigm for representing knowledge. Deffunctions and generic
functions allow the user to define new executable elements in CLIPS that perform a useful
side-effect or return a useful value. These new functions can be called just like the built-in
functions of CLIPS. Message-handlers allow the user to define the behavior of objects by
specifying their response to messages. Deffunctions, generic functions and message-handlers are
all procedural pieces of code specified by the user that CLIPS executes interpretively at the
appropriate times. Defmodules allow a knowledge base to be partitioned.

2.5.2.1 Deffunctions

Deffunctions allow you to define new functions in CLIPS directly (as opposed to user-defined
functions which are written in an external language such as C or Java). The body of a deffunction
is a series of expressions similar to the RHS of a rule that are executed in order by CLIPS when
the deffunction is called. The return value of a deffunction is the value of the last expression
evaluated within the deffunction. Calling a deffunction is identical to calling any other function in
CLIPS.

2.5.2.2 Generic Functions

Generic functions are similar to deffunctions in that they can be used to define new procedural
code directly in CLIPS, and they can be called like any other function. However, generic functions
are much more powerful because they can be overloaded. A generic function will do different
things depending on the types (or classes) and number of its arguments. Generic functions are
comprised of multiple components called methods, where each method handles different cases of
arguments for the generic function. For example, you might overload the “+” operator to do string
concatenation when it is passed strings as arguments. However, the “+” operator will still perform
arithmetic addition when passed numbers. There are two methods in this example: an explicit one
for strings defined by the user and an implicit one which is the standard CLIPS arithmetic addition
operator. The return value of a generic function is the evaluation of the last expression in the
method executed.

2.5.2.3 Object Message-Passing

Objects are described in two basic parts: properties and behavior. Object properties are specified
in terms of slots obtained from the object’s class. Object behavior is specified in terms of
procedural code called message-handlers which are attached to the object’s class. Objects are
manipulated via message-passing. For example, to cause the Rolls-Royce object, which is an
instance of the class CAR, to start its engine, the user must call the send function to send the
message “start-engine” to the Rolls-Royce. How the Rolls-Royce responds to this message will be
dictated by the execution of the message-handlers for “start-engine” attached to the CAR class and

```
16 Section 2: CLIPS Overview
```

any of its superclasses. The result of a message is similar to a function call in CLIPS: a useful
return value or side-effect.

2.5.2.4 Defmodules

Defmodules allow a knowledge base to be partitioned. Every construct defined must be placed in
a module. The programmer can explicitly control which constructs in a module are visible to other
modules and which constructs from other modules are visible to a module. The visibility of facts
and instances between modules can be controlled in a similar manner. Modules can also be used
to control the flow of execution of rules.

### 2.6 CLIPS Object-Oriented Language

This section gives a brief overview of the programming elements of the CLIPS Object-Oriented
Language (COOL). COOL includes elements of data abstraction and knowledge representation.
This section gives an overview of COOL as a whole, incorporating the elements of both concepts.

#### 2.6.1 COOL Deviations from a Pure OOP Paradigm

In a pure OOP language, all programming elements are objects which can only be manipulated via
messages. In CLIPS, the definition of an object is much more constrained: floating-point and
integer numbers, symbols, strings, multifield values, external-addresses, fact-addresses and
instances of user-defined classes. All objects may be manipulated with messages, except instances
of user-defined classes, which must be. For example, in a pure OOP system, to add two numbers
together, you would send the message “add” to the first number object with the second number
object as an argument. In CLIPS, you may simply call the “+” function with the two numbers as
arguments, or you can define message-handlers for the NUMBER class which allow you to do it
in the purely OOP fashion.

All programming elements that are not objects must be manipulated in a non-OOP utilizing
function tailored for those programming elements. For example, to print a rule, you call the
ppdefrule command; you do not send a message “print” to a rule, since it is not an object.

#### 2.6.2 Primary OOP Features

OOP systems have five primary characteristics: abstraction, encapsulation, inheritance,
polymorphism, and dynamic binding. An abstraction is a higher level, more intuitive
representation for a complex concept. Encapsulation is the process whereby the implementation
details of an object are masked by a well-defined external interface. Classes may be described in
terms of other classes by use of inheritance. Polymorphism is the ability of different objects to

```
CLIPS Basic Programming Guide 17
```

respond to the same message in a specialized manner. Dynamic binding is the ability to defer the
selection of which specific message-handlers will be called for a message until run-time.

The definition of new classes allows the abstraction of new data types in COOL. The slots and
message-handlers of these classes describe the properties and behavior of a new group of objects.

COOL supports encapsulation by requiring message-passing for the manipulation of instances of
user-defined classes. An instance cannot respond to a message for which it does not have a defined
message-handler.

COOL allows the user to specify some or all of the properties and behavior of a class in terms of
one or more unrelated superclasses. This process is called multiple inheritance. COOL uses the
existing hierarchy of classes to establish a linear ordering called the class precedence list for a
new class. Objects that are instances of this new class can inherit properties (slots) and behavior
(message-handlers) from each of the classes in the class precedence list. The word precedence
implies that properties and behavior of a class first in the list override conflicting definitions of a
class later in the list.

One COOL object can respond to a message in a completely different way than another object;
this is polymorphism. This is accomplished by attaching message-handlers with differing actions
but which have the same name to the classes of these two objects respectively.

Dynamic binding is supported in that an object reference in a send function call is not bound until
run-time. For example, an instance-name or variable might refer to one object at the time a message
is sent and another at a later time.

#### 2.6.3 Instance-set Queries and Distributed Actions

In addition to the ability of rules to directly pattern-match on objects, COOL provides a useful
query system for determining, grouping and performing actions on sets of instances of user-defined
classes that meet user-defined criteria. The query system allows you to associate instances that are
either related or not. You can simply use the query system to determine if a particular association
set exists, save the set for future reference, or iterate an action over the set. An example of the use
of the query system might be to find the set of all pairs of boys and girls that have the same age.

```
18 Section 3: Deftemplate Construct
```

## Section 3: Deftemplate Construct

Ordered facts encode information positionally. To access that information, a user must know not
only what data is stored in a fact but also which field contains the data. Non-ordered (or
deftemplate) facts provide the user with the ability to abstract the structure of a fact by assigning
names to each field found within the fact. The deftemplate construct is used to create a template
that can then be used by non-ordered facts to access fields of the fact by name. The deftemplate
construct is analogous to a record or structure definition in programming languages such as C.

Syntax

```
(deftemplate <deftemplate-name> [<comment>]
<slot-definition>*)
```

```
<slot-definition> ::= <single-slot-definition> |
<multislot-definition>
```

```
<single-slot-definition>
::= (slot <slot-name>
<template-attribute>*)
```

```
<multislot-definition>
::= (multislot <slot-name>
<template-attribute>*)
```

```
<template-attribute> ::= <default-attribute> |
<constraint-attribute>
```

```
<default-attribute>
::= (default ?DERIVE | ?NONE | <expression>*) |
(default-dynamic <expression>*)
```

Redefining a deftemplate will result in the previous definition being discarded. A deftemplate can
not be redefined while it is being used (for example, by a fact or pattern in a rule). A deftemplate
can have any number of single or multifield slots. CLIPS always enforces the single and multifield
definitions of the deftemplate. For example, it is an error to store (or match) multiple values in a
single-field slot.

```
CLIPS Basic Programming Guide 19
```

Example

```
(deftemplate thing
(slot name)
(slot location)
(slot on-top-of)
(slot weight)
(multislot contents))
```

### 3.1 Slot Default Values

The <default-attribute> specifies the value to be used for unspecified slots of a template fact when
an assert action is performed. One of two types of default selections can be chosen: default or
dynamic-default.

The default attribute specifies a static default value. The specified expressions are evaluated once
when the deftemplate is defined and the result is stored with the deftemplate. The result is assigned
to the appropriate slot when a new template fact is asserted. If the keyword ?DERIVE is used for
the default value, then a default value is derived from the constraints for the slot (see section 11.5
for more details). By default, the default attribute for a slot is (default ?DERIVE). If the keyword
?NONE is used for the default value, then a value must explicitly be assigned for a slot when an
assert is performed. It is an error to assert a template fact without specifying the values for the
(default ?NONE) slots.

The default-dynamic attribute is a dynamic default. The specified expressions are evaluated every
time a template fact is asserted, and the result is assigned to the appropriate slot.

A single-field slot may only have a single value for its default. Any number of values may be
specified as the default for a multifield slot (as long as the number of values satisfies the cardinality
attribute for the slot).

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate point
(slot x (default ?NONE))
(slot y (type INTEGER) (default ?DERIVE))
(slot id (default (gensym*)))
(slot uid (default-dynamic (gensym*))))
CLIPS> (assert (point))
```

```
[TMPLTRHS1] Slot 'x' requires a value because of its (default ?NONE) attribute.
CLIPS> (assert (point (x 3)))
<Fact-1>
CLIPS> (assert (point (x 4)))
<Fact-2>
```

```
20 Section 3: Deftemplate Construct
```

```
CLIPS> (facts)
f-1 (point (x 3) (y 0) (id gen1) (uid gen2))
f-2 (point (x 4) (y 0) (id gen1) (uid gen3))
For a total of 2 facts.
CLIPS>
```

### 3.2 Slot Default Constraints for Pattern-Matching

Single-field slots that are not specified in a pattern on the LHS of a rule are defaulted to single-field
wildcards (?) and multifield slots are defaulted to multifield wildcards ($?).

### 3.3 Slot Value Constraint Attributes

The syntax and functionality of single and multifield constraint attributes are described in detail in
Section 11. Static and dynamic constraint checking for deftemplates is supported. Static checking
is performed when constructs or commands using deftemplates slots are being parsed (and the
specific deftemplate associated with the construct or command can be immediately determined).
Template patterns used on the LHS of a rule are also checked to determine if constraint conflicts
exist among variables used in more than one slot. Errors for inappropriate values are immediately
signaled. References to fact-indexes made in commands such as modify and duplicate are
considered to be ambiguous and are never checked using static checking. Static checking is always
enabled. Dynamic checking is also supported. If dynamic checking is enabled, then new
deftemplate facts have their values checked when created. This dynamic checking is disabled by
default. This behavior can be changed using the set-dynamic-constraint-checking function. If a
violation occurs when dynamic checking is being performed, then execution will be halted.

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

```
CLIPS Basic Programming Guide 21
```

### 3.4 Implied Deftemplates

Asserting or referring to an ordered fact (such as in a LHS pattern) creates an “implied”
deftemplate with a single implied multifield slot named implied. The implied multifield slot’s
name is not printed when the fact is printed. The implied deftemplate can be manipulated and
examined identically to any user defined deftemplate.

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

```
22 Section 4: Deffacts Construct
```

## Section 4: Deffacts Construct

With the deffacts construct, a list of facts can be defined which are automatically asserted
whenever the reset command is performed. Facts asserted through deffacts may be retracted or
pattern-matched like any other fact. The initial fact-list, including any defined deffacts, is always
reconstructed after a reset command.

Syntax

```
(deffacts <deffacts-name> [<comment>]
<RHS-pattern>*)
```

Redefining a currently existing deffacts causes the previous deffacts with the same name to be
removed even if the new definition has errors in it. There may be multiple deffacts constructs and
any number of facts (either ordered or deftemplate) may be asserted into the initial fact-list by each
deffacts construct.

Dynamic expressions may be included in a fact by embedding the expression directly within the
fact. All such expressions are evaluated when CLIPS is reset.

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate oav
(slot object)
(slot attribute)
(slot value))
CLIPS>
(deffacts startup "Refrigerator Status"
(oav (object refrigerator)
(attribute light)
(value on))
(oav (object refrigerator)
(attribute door)
(value open))
(oav (object refrigerator)
(attribute temp)
(value 40)))
CLIPS> (facts)
CLIPS> (reset)
CLIPS> (facts)
f-1 (oav (object refrigerator) (attribute light) (value on))
f-2 (oav (object refrigerator) (attribute door) (value open))
f-3 (oav (object refrigerator) (attribute temp) (value 40))
For a total of 3 facts.
```

CLIPS Basic Programming Guide 23

```
CLIPS>
```

```
24 Section 5: Defrule Construct
```

## Section 5: Defrule Construct

One of the primary methods of representing knowledge in CLIPS are rules. A rule is a collection
of conditions and the actions to be taken if the conditions are satisfied. The developer of an expert
system defines the rules that describe how to solve a problem. Rules execute (or fire) based on the
existence or non-existence of facts or instances of user-defined classes. CLIPS provides the
mechanism (the inference engine) which attempts to match the rules to the current state of the
system (as represented by the fact-list and instance-list) and applies the actions.

Throughout this section, the term pattern entity will be used to refer to either a fact or an instance
of a user-defined class.

### 5.1 Defining Rules

Rules are defined using the defrule construct.

Syntax

```
(defrule <rule-name> [<comment>]
[<declaration>] ; Rule Properties
<conditional-element>* ; Left-Hand Side (LHS)
=>
<action>*) ; Right-Hand Side (RHS)
```

Redefining a currently existing defrule causes the previous defrule with the same name to be
removed even if the new definition has errors in it. The LHS is made up of a series of conditional
elements (CEs) that typically consist of pattern conditional elements (or just simply patterns) to be
matched against pattern entities. An implicit and conditional element always surrounds all the
patterns on the LHS. The RHS contains a list of actions to be performed when the LHS of the rule
is satisfied. In addition, the LHS of a rule may also contain declarations about the rule’s properties
immediately following the rule’s name and comment. The arrow (=>) separates the LHS from the
RHS. Actions are performed sequentially if, and only if, all conditional elements on the LHS are
satisfied.

If no conditional elements are on the LHS, the rule will automatically be activated. If no actions
are on the RHS, the rule can be activated and fired but nothing will happen.

As rules are defined, they are incrementally reset. This means that CEs in newly defined rules can
be satisfied by pattern entities at the time the rule is defined, in addition to pattern entities created
after the rule is defined.

```
CLIPS Basic Programming Guide 25
```

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
0 example-rule: f-1,f- 2
For a total of 1 activation.
CLIPS> (run)
CLIPS> (facts)
f-1 (oav (object refrigerator) (attribute light) (value on))
f-2 (oav (object refrigerator) (attribute door) (value open))
f-3 (oav (object refrigerator) (attribute food) (value spoiled))
For a total of 3 facts.
CLIPS>
```

### 5.2 Basic Cycle Of Rule Execution

Once a knowledge base (in the form of rules) is built and the fact-list and instance-list is prepared,
CLIPS is ready to execute rules. In a conventional language the programmer explicitly defines the
starting point, the stopping point, and the sequence of operations. With CLIPS, the program flow
does not need to be defined explicitly. The knowledge (rules) and the data (facts and instances)
are separated, and the inference engine provided by CLIPS is used to apply the knowledge to the
data. The basic execution cycle is as follows:

```
a) If the rule firing limit has been reached or there is no current focus, then execution is halted.
Otherwise, the top rule on the agenda of the module that is the current focus is selected for
```

```
26 Section 5: Defrule Construct
```

```
execution. If there are no rules on that agenda, then the current focus is removed from the
focus stack and the current focus becomes the next module on the focus stack. If the focus
stack is empty, then execution is halted, otherwise step a is executed again.
```

```
b) The right-hand side (RHS) actions of the selected rule are executed. The use of the return
function on the RHS of a rule may remove the current focus from the focus stack. The number
of rules fired is incremented for use with the rule firing limit.
```

```
c) As a result of step b, rules may be activated or deactivated. Activated rules (those rules
whose conditions are currently satisfied) are placed on the agenda of the module in which
they are defined. The placement on the agenda is determined by the salience of the rule and
the current conflict resolution strategy. Deactivated rules are removed from the agenda. If
the activations item is being watched (as a result of the watch command), then an
informational message will be displayed each time a rule is activated or deactivated.
```

```
d) If dynamic salience is being used (see the set-salience-evaluation command), the salience
values for all rules on the agenda are reevaluated. Repeat the cycle beginning with step a.
```

### 5.3 Conflict Resolution Strategies

The agenda is the list of all rules that have their conditions satisfied (and have not yet been
executed). Each module has its own agenda. The agenda acts similar to a stack (the top rule on the
agenda is the first one to be executed). When a rule is newly activated, its placement on the agenda
is based (in order) on the following factors:

```
a) Newly activated rules are placed above all rules of lower salience and below all rules of higher
salience.
```

```
b) Among rules of equal salience, the current conflict resolution strategy is used to determine
the placement among the other rules of equal salience.
```

```
c) If a rule is activated (along with several other rules) by the same assertion or retraction of a
fact, and steps a and b are unable to specify an ordering, then the rule is arbitrarily (not
randomly) ordered in relation to the other rules with which it was activated. Note, in this
respect, the order in which rules are defined has an arbitrary effect on conflict resolution
(which is highly dependent upon the current underlying implementation of rules). Do not
depend upon this arbitrary ordering for the proper execution of your rules.
```

CLIPS provides seven conflict resolution strategies: depth, breadth, simplicity, complexity, lex,
mea, and random. The default strategy is depth. The current strategy can be set by using the
set-strategy command (which will reorder the agenda based upon the new strategy).

```
CLIPS Basic Programming Guide 27
```

5.3.1 Depth Strategy

Newly activated rules are placed above all rules of the same salience. For example, given that
fact-a activates rule-1 and rule-2 and fact-b activates rule-3 and rule-4, then if fact-a is asserted
before fact-b, rule-3 and rule-4 will be above rule-1 and rule-2 on the agenda. However, the
position of rule-1 relative to rule-2 and rule-3 relative to rule-4 will be arbitrary.

#### 5.3.2 Breadth Strategy........................................................................................................

Newly activated rules are placed below all rules of the same salience. For example, given that
fact-a activates rule-1 and rule-2 and fact-b activates rule-3 and rule-4, then if fact-a is asserted
before fact-b, rule-1 and rule-2 will be above rule-3 and rule-4 on the agenda. However, the
position of rule-1 relative to rule-2 and rule-3 relative to rule-4 will be arbitrary.

#### 5.3.3 Simplicity Strategy....................................................................................................

Among rules of the same salience, newly activated rules are placed above all activations of rules
with equal or higher specificity. The specificity of a rule is determined by the number of
comparisons that must be performed on the LHS of the rule. Each comparison to a constant or
previously bound variable adds one to the specificity. Each function call made on the LHS of a
rule as part of the :, =, or test conditional element adds one to the specificity. The boolean functions
and, or, and not do not add to the specificity of a rule, but their arguments do. Function calls made
within a function call do not add to the specificity of a rule. For example, the following rule

```
(deftemplate point
(slot x)
(slot y)
(slot z))
```

```
(defrule example
(point (x ?x) (y ?y) (z ?x))
(test (and (numberp ?x) (> ?x (+ 10 ?y)) (< ?x 100)))
=>)
```

has a specificity of 5. The comparison to the constant item, the comparison of ?x to its previous
binding, and the calls to the numberp, <, and > functions each add one to the specificity for a total
of 5. The calls to the and and + functions do not add to the specificity of the rule.

#### 5.3.4 Complexity Strategy

Among rules of the same salience, newly activated rules are placed above all activations of rules
with equal or lower specificity.

```
28 Section 5: Defrule Construct
```

#### 5.3.5 LEX Strategy

Among rules of the same salience, newly activated rules are placed using the OPS 5 (an early expert
system tool) strategy of the same name. First the recency of the pattern entities that activated the
rule is used to determine where to place the activation. Every fact and instance is marked internally
with a “time tag” to indicate its relative recency with respect to every other fact and instance in the
system. The pattern entities associated with each rule activation are sorted in descending order for
determining placement. An activation with a more recent pattern entities is placed before
activations with less recent pattern entities. To determine the placement order of two activations,
compare the sorted time tags of the two activations one by one starting with the largest time tags.
The comparison should continue until one activation’s time tag is greater than the other
activation’s corresponding time tag. The activation with the greater time tag is placed before the
other activation on the agenda.

If one activation has more pattern entities than the other activation and the compared time tags are
all identical, then the activation with more time tags is placed before the other activation on the
agenda. If two activations have the exact same recency, the activation with the higher specificity
is placed above the activation with the lower specificity. Unlike OPS5, the not conditional
elements in CLIPS have pseudo time tags that are used by the LEX conflict resolution strategy.
The time tag of a not CE is always less than the time tag of a pattern entity, but greater than the
time tag of a not CE that was instantiated after the not CE in question.

As an example, the following six activations have been listed in their LEX ordering (where the \*
indicates the presence of a not CE). Note that a fact’s time tag is not necessarily the same as it’s
index (since instances are also assigned time tags), but if one fact’s index is greater than another
facts’s index, then it’s time tag is also greater. For this example, assume that the time tags and
indices are the same.

```
rule-6: f-1,f- 4
rule-5: f-1,f-2,f-3,*
rule-1: f-1,f-2,f- 3
rule-2: f-3,f- 1
rule-4: f-1,f-2,*
rule-3: f-2,f- 1
```

Shown following are the same activations with the fact indices sorted as they would be by the LEX
strategy for comparison.

```
rule-6: f-4,f- 1
rule-5: f-3,f-2,f-1,*
rule-1: f-3,f-2,f- 1
rule-2: f-3,f- 1
rule-4: f-2,f-1,*
rule-3: f-2,f- 1
```

```
CLIPS Basic Programming Guide 29
```

#### 5.3.6 MEA Strategy

Among rules of the same salience, newly activated rules are placed using the OPS5 strategy of the
same name. First the time tag of the pattern entity associated with the first pattern is used to
determine where to place the activation. An activation that has a first pattern with a time tag that
is greater than time tag of the first pattern of another activation is placed before the other activation
on the agenda. If both activations have the same time tag associated with the first pattern, then the
LEX strategy is used to determine placement of the activation. Again, as with the CLIPS LEX
strategy, negated patterns have pseudo time tags.

As an example, the following six activations have been listed in their MEA ordering (where the \*
indicates the presence of a negated pattern).

```
rule-2: f-3,f- 1
rule-3: f-2,f- 1
rule-6: f-1,f- 4
rule-5: f-1,f-2,f-3,*
rule-1: f-1,f-2,f- 3
rule-4: f-1,f-2,*
```

#### 5.3.7 Random Strategy

Each activation is assigned a random number that is used to determine its placement among
activations of equal salience. This random number is preserved when the strategy is changed so
that the same ordering is reproduced when the random strategy is selected again (among
activations that were on the agenda when the strategy was originally changed).

❖ Usage Note

A conflict resolution strategy is an implicit mechanism for specifying the order in which rules of
equal salience should be executed. In early expert system tools, this was often the only mechanism
provided to specify the order. Because the mechanism is implicit, it’s not possible to determine
the programmer’s original intent simply by looking at the code. Rather than explicitly indicating
that rule A should be executed before rule B, the order of execution is implicitly determined by
the order in which facts are asserted and the complexity of the rules. The assumption one must
make when examining the code is that the original programmer carefully analyzed the rules and
followed the necessary conventions so that the rules execute in the appropriate sequence.

Because they require explicit declarations, the preferred mechanisms in CLIPS for ordering the
execution of rules are salience and modules. Salience allows one to explicitly specify that one rule
should be executed before another rule. Modules allow one to explicitly specify that all of the rules
in a particular group (module) should be executed before all of the rules in a different group. Thus,
when designing a program the following convention should be followed: if two rules have the
same salience, are in the same module, and are activated concurrently, then the order in which they

```
30 Section 5: Defrule Construct
```

are executed should not matter. For example, the following two rules need correction because they
can be activated at the same time, but the order in which they execute matters:

```
(defrule print-schedules
(classes-scheduled)
=>
(assert (print-schedules)))
```

```
(defrule retry-scheduling
?f <- (classes-scheduled)
(scheduling-errors)
=>
(retract ?f)
(assert (retry-scheduling)))
```

Programmers should also be careful to avoid overusing salience. Trying to unravel the
relationships between dozens of salience values can be just as confusing as the implicit use of a
conflict resolution strategy in determining rule execution order. It’s rarely necessary to use more
than five to ten salience values in a well-designed program.

Most programs should use the default conflict resolution strategy of depth. The breadth, simplicity,
and complexity strategies are provided largely for academic reasons (i.e. the study of conflict
resolution strategies). The lex and mea strategies are provided to help in converting OPS5
programs to CLIPS.

The random strategy is useful for testing. Because this strategy randomly orders activations having
the same salience, it is useful in detecting whether the execution order of rules with the same
salience effects the program behavior. Before running a program with the random strategy, first
seed the random number generator using the seed function. The same seed value can be
subsequently be used if it is necessary to replicate the results of the program run.

### 5.4 LHS Syntax

This section describes the syntax used on the LHS of a rule. The LHS of a CLIPS rule is made up
of a series of conditional elements (CEs) that must be satisfied for the rule to be placed on the
agenda. There are eight types of conditional elements: pattern CEs, test CEs, and CEs, or CEs,
not CEs, exists CEs, forall CEs, and logical CEs. The pattern CE is the most basic and commonly
used conditional element. Pattern CEs contain constraints that are used to determine if any pattern
entities (facts or instances) satisfy the pattern. The test CE is used to evaluate expressions as part
of the pattern-matching process. The and CE is used to specify that an entire group of CEs must
all be satisfied. The or CE is used to specify that only one of a group of CEs must be satisfied. The
not CE is used to specify that a CE must not be satisfied. The exists CE is used to test for the
occurence of at least one partial match for a set of CEs. The forall CE is used to test that a set of
CEs is satisfied for every partial match of a specified CE. Finally, the logical CE allows assertions

```
CLIPS Basic Programming Guide 31
```

of facts and the creation of instances on the RHS of a rule to be logically dependent upon pattern
entities matching patterns on the LHS of a rule (truth maintenance).

Syntax

```
<conditional-element> ::= <pattern-CE> |
<assigned-pattern-CE> |
<not-CE> |
<and-CE> |
<or-CE> |
<logical-CE> |
<test-CE> |
<exists-CE> |
<forall-CE>
```

#### 5.4.1 Pattern Conditional Element

Pattern conditional elements consist of a collection of field constraints, wildcards, and variables
which are used to constrain the set of facts or instances which match the pattern CE. A pattern CE
is satisfied by each and every pattern entity that satisfies its constraints. Field constraints are a set
of constraints that are used to test a single field or slot of a pattern entity. A field constraint may
consist of only a single literal constraint, however, it may also consist of several constraints
connected together. In addition to literal constraints, CLIPS provides three other types of
constraints: connective constraints, predicate constraints, and return value constraints. Wildcards
are used within pattern CEs to indicate that a single field or group of fields can be matched by
anything. Variables are used to store the value of a field so that it can be used later on the LHS of
a rule in other conditional elements or on the RHS of a rule as an argument to an action.

The first field of any pattern must be a symbol and can not use any other constraints. This first
field is used by CLIPS to determine if the pattern applies to an ordered fact, a template fact, or an
instance. The symbol object is reserved to indicate an object pattern. Any other symbol used must
correspond to a deftemplate name (or an implied deftemplate will be created). Slot names must
also be symbols and cannot contain any other constraints.

For object and deftemplate patterns, a single field slot can only contain one field constraint and
that field constraint must only be able to match a single field (no multifield wildcards or variables).
A multifield slot can contain any number of field constraints.

5.4.1.1 Literal Constraints

The most basic constraint that can be used in a pattern CE is one which precisely defines the exact
value that will match a field. This is called a literal constraint. A literal pattern CE consists
entirely of constants such as floats, integers, symbols, strings, and instance names. It does not

```
32 Section 5: Defrule Construct
```

contain any variables or wildcards. All constraints in a literal pattern must be matched exactly by
all fields of a pattern entity.

Syntax

An ordered pattern conditional element containing only literals has the following basic syntax:

```
(<constant-1> ... <constant-n>)
```

A deftemplate pattern conditional element containing only literals has the following basic syntax:

```
(<deftemplate-name> (<slot-name-1> <constant-1>)
```

-
-
- (<slot-name-n> <constant-n>))

Example 1

```
CLIPS> (clear)
CLIPS>
(defrule rgb-primary
(colors rgb primary red green blue)
=>)
CLIPS> (assert (colors ryb secondary purple orange green))
<Fact-1>
CLIPS> (assert (colors rgb primary red green blue))
<Fact-2>
CLIPS> (agenda)
0 rgb-primary: f- 2
For a total of 1 activation.
CLIPS>
```

Example 2

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(multislot name)
(slot age))
CLIPS>
(defrule Find-Joe-Bob
(person (name Joe Bob Green) (age 20))
=>)
CLIPS> (assert (person (name Joe Bob Green) (age 20)))
<Fact-1>
CLIPS> (assert (person (name Ann Green) (age 34)))
<Fact-2>
CLIPS> (agenda)
0 Find-Joe-Bob: f- 1
For a total of 1 activation.
CLIPS>
```

```
CLIPS Basic Programming Guide 33
```

Example 3

```
CLIPS> (clear)
CLIPS>
(defrule approved
(credit-score at-least 720)
(down-payment-percent at-least 0.20)
(monthly-debt-percent no-more-than 0.36)
=>
(assert (loan-approved)))
CLIPS> (watch activations)
CLIPS> (assert (down-payment-percent at-least 0.20))
<Fact-1>
CLIPS> (assert (credit-score at-least 720))
<Fact-2>
CLIPS> (assert (monthly-debt-percent no-more-than 0.36))
==> Activation 0 approved: f-2,f-1,f- 3
<Fact-3>
CLIPS> (watch facts)
CLIPS> (run)
==> f-4 (loan-approved)
CLIPS> (unwatch all)
CLIPS>
```

5.4.1.2 Wildcards Single- and Multifield

CLIPS has two wildcard symbols that may be used to match fields in a pattern. CLIPS interprets
these wildcard symbols as standing in place of some part of a pattern entity. The single-field wild-
card, denoted by a question mark character (?), matches any value stored in exactly one field in
the pattern entity. The multifield wildcard, denoted by a dollar sign followed by a question mark
($?), matches any value in zero or more fields in a pattern entity. Single-field and multifield
wildcards may be combined in a single pattern in any combination. It is illegal to use a multifield
wildcard in a single field slot of a deftemplate or object pattern. By default, an unspecified
single-field slot in a deftemplate/object pattern is matched against an implied single-field wildcard.
Similarly, an unspecified multifield slot in a deftemplate/object pattern is matched against an
implied multifield-wildcard.

Syntax

An ordered pattern conditional element containing only literals and wildcards has the following
basic syntax:

```
(<constraint-1> ... <constraint-n>)
```

where

```
<constraint> ::= <constant> |? | $?
```

```
34 Section 5: Defrule Construct
```

A deftemplate pattern conditional element containing only literals and wildcards has the following
basic syntax:

```
(<deftemplate-name> (<slot-name-1> <constraint-1>)
```

-
-
- (<slot-name-n> <constraint-n>))

Example 1

```
CLIPS> (clear)
CLIPS>
(defrule grocery-list-has-milk
(grocery-list $? milk $?)
=>)
CLIPS> (assert (grocery-list milk eggs cheese))
<Fact-1>
CLIPS> (assert (grocery-list bread onions tomatoes cheese))
<Fact-2>
CLIPS> (agenda)
0 grocery-list-has-milk: f- 1
For a total of 1 activation.
CLIPS>
```

Example 2

```
CLIPS> (clear)
CLIPS>
(defrule at-least- 3 - items
(grocery-list??? $?)
=>)
CLIPS> (assert (grocery-list apple pears))
<Fact-1>
CLIPS> (assert (grocery-list milk eggs cheese))
<Fact-2>
CLIPS> (assert (grocery-list bread onions tomatoes cheese))
<Fact-3>
CLIPS> (agenda)
0 at-least- 3 - items: f- 3
0 at-least- 3 - items: f- 2
For a total of 2 activations.
CLIPS>
```

Example 3

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(multislot name)
(slot age))
CLIPS>
(defrule match-all-persons
```

```
CLIPS Basic Programming Guide 35
```

```
(person)
=>)
CLIPS> (assert (person (name Joe Bob Green) (age 20)))
<Fact-1>
CLIPS> (assert (person (name Ann Green) (age 34)))
<Fact-2>
CLIPS> (agenda)
0 match-all-persons: f- 2
0 match-all-persons: f- 1
For a total of 2 activations.
CLIPS>
```

Example 4

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(multislot name)
(slot age))
CLIPS>
(defrule match-two-names
(person (name? ?))
=>)
CLIPS>
(defrule match-three-names
(person (name?? ?))
=>)
CLIPS> (assert (person (name Joe Bob Green) (age 20)))
<Fact-1>
CLIPS> (assert (person (name Martin Brown) (age 20)))
<Fact-2>
CLIPS> (assert (person (name Frank Samuel Jones Jr.) (age 28)))
<Fact-3>
CLIPS> (agenda)
0 match-two-names: f- 2
0 match-three-names: f- 1
For a total of 2 activations.
CLIPS>
```

Example 5

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(multislot name)
(slot age))
CLIPS>
(defrule last-name-brown
(person (name $? Brown))
=>)
CLIPS>
(defrule name-contains-ann
(person (name $? Ann $?))
=>)
```

```
36 Section 5: Defrule Construct
```

```
CLIPS> (assert (person (name Martin Brown) (age 20)))
<Fact-1>
CLIPS> (assert (person (name Ann Green) (age 34)))
<Fact-2>
CLIPS> (assert (person (name Sue Ann Brown) (age 20)))
<Fact-3>
CLIPS> (agenda)
0 last-name-brown: f- 3
0 name-contains-ann: f- 3
0 name-contains-ann: f- 2
0 last-name-brown: f- 1
For a total of 4 activations.
CLIPS>
```

5.4.1.3 Variables Single- and Multifield

Wildcard symbols replace portions of a pattern and accept any value. The value of the field being
replaced may be captured in a variable for comparison, display, or other manipulations. This is
done by directly following the wildcard symbol with a variable name.

Syntax

Expanding on the syntax definition given in section 5.4.1.2 now gives:

```
<constraint> ::= <constant> |? | $? |
<single-field-variable> |
<multifield-variable>
```

```
<single-field-variable> ::= ?<variable-symbol>
```

```
<multifield-variable> ::= $?<variable-symbol>
```

The term <variable-symbol> is similar to a symbol, except that it must start with an alphabetic
character. Double quotes are not allowed as part of a variable name; i.e. a string cannot be used
for a variable name. The rules for pattern-matching are similar to those for wildcard symbols. On
its first appearance, a variable acts just like a wildcard in that it will bind to any value in the field(s).
However, later appearances of the variable require the field(s) to match the binding of the variable.
The binding will only be true within the scope of the rule in which it occurs. Each rule has its own
list of variable names with their associated values; thus, variables are local to a rule. Bound vari-
ables can be passed to external functions. The $ operator has special significance on the LHS as a
pattern-matching operator to indicate that zero or more fields need to be matched. In other places
(such as the RHS of a rule), the $ in front of a variable indicates that sequence expansion should
take place before calling the function. Thus, when passed as parameters in function calls (either
on the LHS or RHS of a rule), multifield variables should not be preceded by the $ (unless sequence
expansion is desired). All other uses of a multifield variable on the LHS of a rule, however, should
use the $. It is illegal to use a multifield variable in a single field slot of a deftemplate/object
pattern.

```
CLIPS Basic Programming Guide 37
```

Example 1

```
CLIPS> (clear)
CLIPS>
(defrule grocery-list-has-milk
(grocery-list ?id $?b milk $?e)
=>
(println "List " ?id " has milk and " (create$ ?b ?e)))
CLIPS> (assert (grocery-list #1 milk eggs cheese))
<Fact-1>
CLIPS> (assert (grocery-list #2 bread onions tomatoes cheese))
<Fact-2>
CLIPS> (run)
List #1 has milk and (eggs cheese)
CLIPS>
```

Example 2

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(multislot name)
(slot age))
CLIPS>
(defrule print-person
(person (name $?name) (age ?age))
=>
(println (implode$ ?name) " is " ?age " years old"))
CLIPS> (assert (person (name Ann Green) (age 34)))
<Fact-1>
CLIPS> (assert (person (name Sue Ann Brown) (age 20)))
<Fact-2>
CLIPS> (run)
Sue Ann Brown is 20 years old
Ann Green is 34 years old
CLIPS>
```

Example 3

```
CLIPS> (clear)
CLIPS>
(defrule down-payment-percent
(loan-amount ?la)
(available-down-payment ?adp)
=>
(bind ?dpp (/ ?adp ?la))
(assert (down-payment-percent ?dpp)))
CLIPS> (assert (loan-amount 100000))
<Fact-1>
CLIPS> (assert (available-down-payment 25000))
<Fact-2>
CLIPS> (agenda)
0 down-payment-percent: f-1,f- 2
For a total of 1 activation.
```

```
38 Section 5: Defrule Construct
```

```
CLIPS> (watch rules)
CLIPS> (watch facts)
CLIPS> (run)
FIRE 1 down-payment-percent: f-1,f- 2
==> f-3 (down-payment-percent 0.25)
CLIPS> (unwatch all)
CLIPS>
```

Once the initial binding of a variable occurs, all references to that variable have to match the value
that the first binding matched. This applies to both single- and multifield variables. It also applies
across patterns.

Example 4

```
CLIPS> (clear)
CLIPS>
(defrule duplicate-item
(grocery-list ?id $? ?item $? ?item $?)
=>
(println "List " ?id " has duplicate item " ?item))
CLIPS> (assert (grocery-list #1 milk eggs cheese))
<Fact-1>
CLIPS> (assert (grocery-list #2 bread onions bread cheese cheese))
<Fact-2>
CLIPS> (run)
List #2 has duplicate item bread
List #2 has duplicate item cheese
CLIPS>
```

5.4.1.4 Connective Constraints

Three connective constraints are available for connecting individual constraints and variables to
each other. These are the & (and), | (or), and ~ (not) connective constraints. The & constraint is
satisfied if the two adjoining constraints are satisfied. The | constraint is satisfied if either of the
two adjoining constraints is satisfied. The ~ constraint is satisfied if the following constraint is not
satisfied. Multiple connective constraints can be chained together. The ~ constraint has highest
precedence, followed by the & constraint, followed by the | constraint. Otherwise, evaluation of
multiple constraints can be considered to occur from left to right. There is one exception to the
precedence rules that applies to the binding occurrence of a variable. If the first constraint is a
variable followed by an & connective constraint, then the first constraint is treated as a separate
constraint which also must be satisified. Thus the constraint ?x&red|blue is treated as ?x & red|blue
rather than ?x&red | blue as the normal precedence rules would indicate.

Syntax

Expanding on the syntax definition given in section 5.4.1.3 now gives:

```
<constraint> ::=? | $? | <connected-constraint>
```

```
CLIPS Basic Programming Guide 39
```

```
<connected-constraint>
::= <single-constraint> |
<single-constraint> & <connected-constraint> |
<single-constraint> | <connected-constraint>
```

```
<single-constraint> ::= <term> | ~<term>
```

```
<term> ::= <constant> |
<single-field-variable> |
<multifield-variable>
```

Note that the vertical bar in the "<single-constraint> | <connected-constraint>" non-terminal
choice is the | character (which must be included in the text of the constraint) and does not indicate
a choice between multiple BNF terms.

The & constraint typically is used only in conjunction with other constraints or variable bindings.
Notice that connective constraints may be used together and/or with variable bindings. If the first
term of a connective constraint is the first occurrence of a variable name, then the field will be
constrained only by the remaining field constraints. The variable will be bound to the value of the
field. If the variable has been bound previously, it is considered an additional constraint along with
the remaining field constraints; i.e., the field must have the same value already bound to the
variable and must satisfy the field constraints.

Example 1

```
CLIPS> (clear)
CLIPS>
(defrule dairy-product
(grocery-list $? milk | butter | cream $?)
=>
(println "Grocery list contains dairy product"))
CLIPS>
(defrule non-dairy-product
(grocery-list $? ~milk&~butter&~cream $?)
=>
(println "Grocery list contains non-dairy product"))
CLIPS> (assert (grocery-list butter eggs cream bread salt))
<Fact-1>
CLIPS> (agenda)
0 non-dairy-product: f- 1
0 non-dairy-product: f- 1
0 non-dairy-product: f- 1
0 dairy-product: f- 1
0 dairy-product: f- 1
For a total of 5 activations.
CLIPS>
```

Example 2

```
CLIPS> (clear)
```

```
40 Section 5: Defrule Construct
```

```
CLIPS>
(defrule dairy-product
(grocery-list $? ?product&milk|butter|cream $?)
=>
(println "Dairy product: " ?product))
CLIPS>
(defrule non-dairy-product
(grocery-list $? ?product&~milk&~butter&~cream $?)
=>
(println "Non-dairy product: " ?product))
CLIPS> (assert (grocery-list butter eggs cream bread salt))
<Fact-1>
CLIPS> (agenda)
0 dairy-product: f- 1
0 non-dairy-product: f- 1
0 dairy-product: f- 1
0 non-dairy-product: f- 1
0 non-dairy-product: f- 1
For a total of 5 activations.
CLIPS> (run)
Dairy product: butter
Non-dairy product: eggs
Dairy product: cream
Non-dairy product: bread
Non-dairy product: salt
CLIPS>
```

Example 3

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(multislot name))
CLIPS>
(defrule may-be-related
(person (name $?first1 ?last))
(person (name $?first2&~$?first1 ?last))
=>
(println (implode$ ?first1) " " ?last " may be related to "
(implode$ ?first2) " " ?last "."))
CLIPS> (assert (person (name Joe Bob Green)))
<Fact-1>
CLIPS> (assert (person (name Martin Brown)))
<Fact-2>
CLIPS> (assert (person (name Sue Ann Brown)))
<Fact-3>
CLIPS> (agenda)
0 may-be-related: f-3,f- 2
0 may-be-related: f-2,f- 3
For a total of 2 activations.
CLIPS> (run)
Sue Ann Brown may be related to Martin Brown.
Martin Brown may be related to Sue Ann Brown.
CLIPS>
```

```
CLIPS Basic Programming Guide 41
```

5.4.1.5 Predicate Constraints

CLIPS allows the use of a predicate constraint to restrict a field based on the value returned by
a function call. The predicate constraint allows a predicate function (one returning the symbol
FALSE for unsatisfied and a non-FALSE value for satisfied) to be called during the
pattern-matching process. If the predicate function returns a non-FALSE value, the constraint is
satisfied. If the predicate function returns the symbol FALSE, the constraint is not satisfied. A
predicate constraint is invoked by following a colon with a function call to a predicate function.
Typically, predicate constraints are used in conjunction with a connective constraint and a variable
binding (i.e. you have to bind the variable to be tested and then connect it to the predicate
constraint).

Basic Syntax

```
:<function-call>
```

Syntax

Expanding on the syntax definition given in section 5.4.1.4 now gives:

```
<term> ::= <constant> |
<single-field-variable> |
<multifield-variable> |
:<function-call>
```

Multiple predicate constraints may be used to constrain a single field. CLIPS provides several
predefined predicate functions and users may also create their own. Although any function may be
called by the predicate constraint, unless the function returns FALSE for some arguments and a
non-FALSE value for other arguments, the predicate constraint will either always fail or always
succeed.

Example 1

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
(slot age))
CLIPS>
(defrule adult
(person (age ?age&:(>= ?age 18)))
=>)
CLIPS>
(assert (person (name John) (age 20)) ; f- 1
(person (name Sally) (age 18)) ; f- 2
(person (name Bill) (age 14))) ; f- 3
<Fact-3>
CLIPS> (agenda)
0 adult: f- 2
```

```
42 Section 5: Defrule Construct
```

```
0 adult: f- 1
For a total of 2 activations.
CLIPS>
```

Example 2

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
(multislot attributes))
CLIPS>
(defrule not-tall
(person (attributes $?a&~:(member$ tall ?a)))
=>)
CLIPS>
(assert (person (name John) (attributes tall thin)) ; f- 1
(person (name Greg) (attributes short stout)) ; f- 2
(person (name Jill) (attributes young tall))) ; f- 3
<Fact-3>
CLIPS> (agenda)
0 not-tall: f- 2
For a total of 1 activation.
CLIPS>
```

Example 3

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
(slot age))
CLIPS>
(defrule teenager
(person (age ?age&:(>= ?age 13)&:(<= ?age 19)))
=>)
CLIPS>
(assert (person (name John) (age 20)) ; f- 1
(person (name Sally) (age 18)) ; f- 2
(person (name Bill) (age 14))) ; f- 3
<Fact-3>
CLIPS> (agenda)
0 teenager: f- 3
0 teenager: f- 2
For a total of 2 activations.
CLIPS>
```

Example 4

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
(slot age))
```

```
CLIPS Basic Programming Guide 43
```

```
CLIPS>
(defrule older
(person (age ?age1))
(person (age ?age2&:(> ?age1 ?age2)))
=>)
CLIPS>
(assert (person (name John) (age 20)) ; f- 1
(person (name Sally) (age 18)) ; f- 2
(person (name Bill) (age 14))) ; f- 3
<Fact-3>
CLIPS> (agenda)
0 older: f- 1 ,f- 3
0 older: f-2,f- 3
0 older: f-1,f- 2
For a total of 3 activations.
CLIPS>
```

Example 5

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
(multislot siblings))
CLIPS>
(defrule large-family
(person (siblings $?s&:(> (length$ ?s) 4)))
=>)
CLIPS>
(assert (person (name John) (siblings Fred Gwen)) ; f- 1
(person (name Greg)) ; f- 2
(person (name Jill) (siblings Joe Sue Lou Mark Dot))) ; f- 3
<Fact-3>
CLIPS> (agenda)
0 large-family: f- 3
For a total of 1 activation.
CLIPS>
```

Example 6

```
CLIPS> (clear)
CLIPS>
(defrule sort
?f <- (numbers $?b ?v1 ?v2&:(> ?v1 ?v2) $?e)
=>
(retract ?f)
(assert (numbers ?b ?v2 ?v1 ?e)))
CLIPS> (assert (numbers 8 3 6 9 2 3 7))
<Fact-1>
CLIPS> (run)
CLIPS> (facts)
f-12 (numbers 2 3 3 6 7 8 9)
For a total of 1 fact.
CLIPS>
```

```
44 Section 5: Defrule Construct
```

Example 7

```
CLIPS> (clear)
CLIPS>
(defrule at-least- 3 - items
(grocery-list $?list&:(>= (length$ ?list) 3))
(test (>= (length$ ?list) 3))
=>)
CLIPS> (assert (grocery-list apple pears))
<Fact-1>
CLIPS> (assert (grocery-list milk eggs cheese))
<Fact-2>
CLIPS> (assert (grocery-list bread onions tomatoes cheese))
<Fact-3>
CLIPS> (agenda)
0 at-least- 3 - items: f- 3
0 at-least- 3 - items: f- 2
For a total of 2 activations.
CLIPS>
```

Example 8

```
CLIPS> (clear)
CLIPS>
(defrule approved
(credit-score ?cs&:(>= ?cs 720))
(down-payment-percent ?dpp&:(>= ?dpp 0.20))
(monthly-debt-percent ?mdp&:(<= ?mdp 0.36))
=>
(assert (loan-approved)))
CLIPS> (assert (monthly-debt-percent 0.3))
<Fact-1>
CLIPS> (assert (down-payment-percent 0.25))
<Fact-2>
CLIPS> (assert (credit-score 800))
<Fact-3>
CLIPS> (agenda)
0 approved: f-3,f-2,f- 1
For a total of 1 activation.
CLIPS> (watch facts)
CLIPS> (run)
==> f-4 (loan-approved)
CLIPS> (unwatch facts)
CLIPS>
```

5.4.1.6 Return Value Constraints

The return value constraint (=) allows constraining the value of field to the return value of a
function. (This constraint is different from the numeric comparison function that uses the same
symbol. The difference can be determined from context.) The return value must be one of the
single field primitive data types. This value is incorporated directly into the pattern at the position

```
CLIPS Basic Programming Guide 45
```

at which the function was called as if it were a literal constraint, and any matching patterns must
match this value as though the rule was defined with that value. Note that the function is evaluated
each time the constraint is checked (not just once when the rule is defined).

Basic Syntax

```
=<function-call>
```

Syntax

Expanding on the syntax definition given in section 5.4.1.5 now gives:

```
<term> ::= <constant> |
<single-field-variable> |
<multifield-variable> |
:<function-call> |
=<function-call>
```

Example 1

```
CLIPS> (clear)
CLIPS>
(defrule ask-question
=>
(bind ?length (random 1 10))
(bind ?width (random 1 10))
(println "A rectangle has length " ?length " and width " ?width)
(print "What is the area of this rectangle? ")
(assert (response ?length ?width (read))))
CLIPS>
(defrule correct-area
(response ?length ?width =(* ?length ?width))
=>
(println "You are correct!"))
CLIPS>
(defrule incorrect-area
(response ?length ?width ~=(* ?length ?width))
=>
(println "You are incorrect!"))
CLIPS> (run)
A rectangle has length 8 and width 10
What is the area of this rectangle? 80
You are correct!
CLIPS> (reset)
CLIPS> (run)
A rectangle has length 4 and width 4
What is the area of this rectangle? 8
You are incorrect!
CLIPS>
```

```
46 Section 5: Defrule Construct
```

Example 2

```
CLIPS> (clear)
CLIPS>
(deftemplate hoo "hours of operation"
(slot day)
(slot open)
(slot close))
CLIPS>
(deffacts hoos
(hoo (day Monday) (open "8:00 am") (close "6:00 pm"))
(hoo (day Tuesday) (open "8:00 am") (close "7:00 pm"))
(hoo (day Wednesday) (open "8:00 am") (close "6:00 pm"))
(hoo (day Thursday) (open "8:00 am") (close "5:00 pm"))
(hoo (day Friday) (open "8:00 am") (close "12:00 pm"))
(hoo (day Saturday) (open "8:30 am") (close "11:30 am")))
CLIPS>
(deffunction weekday ()
(nth$ 7 (local-time)))
CLIPS>
(defrule today's-hours
(hoo (day =(weekday)) (open ?open) (close ?close))
=>
(println "We are open today from " ?open " to " ?close "."))
CLIPS>
(defrule closed-today
(not (hoo (day =(weekday))))
=>
(println "We are closed today."))
CLIPS> (reset)
CLIPS> (run)
We are open today from 8:00 am to 6:00 pm.
CLIPS>
```

5.4.1.7 Pattern-Matching with Object Patterns

Instances of user-defined classes in COOL can be pattern-matched on the left-hand side of rules.
Patterns can only match objects for which the object’s most specific class is defined before the
pattern and which are in scope for the current module. Any classes that could have objects that
match the pattern cannot be deleted or changed until the pattern is deleted. Even if a rule is deleted
by its RHS, the classes bound to its patterns cannot be changed until after the RHS finishes
executing.

When an instance is created or deleted, all patterns applicable to that object are updated. However,
when a slot is changed, only those patterns that explicitly match on that slot are affected. Thus,
one could use logical dependencies to hook to a change to a particular slot (rather than a change
to any slot, which is all that is possible with deftemplates).

```
CLIPS Basic Programming Guide 47
```

Changes to non-reactive slots or instances of non-reactive classes will have no effect on rules. Also
Rete network activity will not be immediately apparent after changes to slots are made if
pattern-matching is being delayed through the use of the make-instance, initialize-instance,
modify-instance, message-modify-instance, duplicate-instance, message-duplicate-instance
or object-pattern-match-delay functions.

Syntax

```
<object-pattern> ::= (object <attribute-constraint>*)
```

```
<attribute-constraint> ::= (is-a <constraint>) |
(name <constraint>) |
(<slot-name> <constraint>*)
```

The is-a constraint is used for specifying class constraints such as “Is this object a member of class
PERSON?”. The is-a constraint also encompasses subclasses of the matching classes unless
specifically excluded by the pattern. The name constraint is used for specifying a specific instance
on which to pattern-match. The evaluation of the name constraint must be of primitive type
instance-name, not symbol. Multifield constraints (such as $?) cannot be used with the is-a or
name constraints. Other than these special cases, constraints used in object slots work similarly to
constraints used in deftemplate slots. As with deftemplate patterns, slot names for object patterns
must be symbols and can not contain any other constraints.

Example 1

The following rules illustrate pattern-matching on an object's class.

```
(defrule class-match- 1
(object)
=>)
```

```
(defrule class-match- 2
(object (is-a PERSON))
=>)
```

```
(defrule class-match- 3
(object (is-a MAN | WOMAN))
=>)
```

```
(defrule class-match- 4
(object (is-a ?x))
(object (is-a ~?x))
=>)
```

Rule class-match- 1 is satisified by all instances of any reactive class. Rule class-match- 2 is
satisfied by all instances of class PERSON. Rule class-match- 3 is satisfied by all instances of class
MAN or WOMAN. Rule class-match- 4 will be satisfied by any two instances of mutually
exclusive classes.

```
48 Section 5: Defrule Construct
```

Example 2

The following rules illustrate pattern-matching on various attributes of an object's slots.

```
(defrule slot-match- 1
(object (width))
=>)
```

```
(defrule slot-match- 2
(object (width ?))
=>)
```

```
(defrule slot-match- 3
(object (width $?))
=>)
```

Rule slot-match- 1 is satisfied by all instances of reactive classes that contain a reactive width slot
with a zero length multifield value. Rule slot-match- 2 is satisfied by all instances of reactive classes
that contain a reactive single or multifield width slot that is bound to a single value. Rule
slot-match- 3 is satisfied by all instances of reactive classes that contain a reactive single or
multifield width slot that is bound to any number of values. Note that a slot containing a zero length
multifield value would satisfy rules slot-match- 1 and slot-match- 3 , but not rule slot-match- 2
(because the value's cardinality is zero).

Example 3

The following rules illustrate pattern-matching on the slot values of an object.

```
(defrule value-match- 1
(object (width 10)
=>)
```

```
(defrule value-match- 2
(object (width ?x&:(> ?x 20)))
=>)
```

```
(defrule value-match- 3
(object (width ?x) (height ?x))
=>)
```

Rule value-match- 1 is satisified by all instances of reactive classes that contain a reactive width
slot with value 10. Rule value-match- 2 is satisfied by all instances of reactive classes that contain
a reactive width slot that has a value greater than 20. Rule value-match- 3 is satisfied by all instances
of reactive classes that contain a reactive width and height slots with the same value.

```
CLIPS Basic Programming Guide 49
```

5.4.1.8 Pattern-Addresses

Certain RHS actions, such as retract and unmake-instance, operate on an entire pattern CE. To
signify which fact or instance they are to act upon, a variable can be bound to the fact-address or
instance-address of a pattern CE. Collectively, fact-addresses and instance-addresses bound on
the LHS of a rule are referred to as pattern-addresses.

Syntax

```
<assigned-pattern-CE> ::= ?<variable-symbol> <- <pattern-CE>
```

The left arrow, <-, is a required part of the syntax. A variable bound to a fact-address or
instance-address can be compared to other variables or passed to functions. Variables bound to a
fact or instance-address may later be used to constrain fields within a pattern CE, however, the
reverse is not allowed. It is an error to bind a varible to a not CE.

Example 1

```
CLIPS> (clear)
CLIPS>
(defrule print-grocery-list
?f <- (grocery-list $?items)
=>
(retract ?f)
(println "groceries: " (implode$ ?items)))
CLIPS> (assert (grocery-list milk eggs cheese))
<Fact-1>
CLIPS> (run)
groceries: milk eggs cheese
CLIPS> (facts)
CLIPS>
```

Example 2

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(multislot name))
CLIPS>
(defrule may-be-related
?p1 <- (person (name $?first1 ?last))
?p2 <- (person (name $?first2 ?last))
(test (neq ?p1 ?p2))
=>
(println (implode$ ?first1) " " ?last " may be related to "
(implode$ ?first2) " " ?last "."))
CLIPS> (assert (person (name Joe Bob Green)))
<Fact-1>
CLIPS> (assert (person (name Martin Brown)))
<Fact-2>
CLIPS> (assert (person (name Sue Ann Brown)))
```

```
50 Section 5: Defrule Construct
```

```
<Fact-3>
CLIPS> (agenda)
0 may-be-related: f-3,f- 2
0 may-be-related: f-2,f- 3
For a total of 2 activations.
CLIPS> (run)
Sue Ann Brown may be related to Martin Brown.
Martin Brown may be related to Sue Ann Brown.
CLIPS>
```

Example 3

```
CLIPS> (clear)
CLIPS>
(defclass PERSON
(is-a USER)
(slot sname)
(slot age))
CLIPS> (make-instance [p1] of PERSON (sname "Sam Jones") (age 77))
[p1]
CLIPS> (make-instance [p2] of PERSON (sname "Sally Smith") (age 25))
[p2]
CLIPS>
(defrule print-and-delete-all-objects
?ins <- (object)
=>
(send ?ins print)
(unmake-instance ?ins))
CLIPS> (run)
[p2] of PERSON
(sname "Sally Smith")
(age 25)
[p1] of PERSON
(sname "Sam Jones")
(age 77)
CLIPS> (instances)
CLIPS>
```

#### 5.4.2 Test Conditional Element

The test conditional element is used to evaluate a function call. The test CE is unsatisfied if the
associated function call returns the symbol FALSE and satisfied if any other value is returned. As
with predicate constraints, the user can reference variables that were previously bound.

Syntax

```
<test-CE> ::= (test <function-call>)
```

Since the symbol test is used to indicate this type of conditional element, rules may not use the
symbol test as the first field in a pattern CE. A test CE is evaluated when all proceeding CEs are
satisfied. This means that a test CE will be evaluated more than once if the proceeding CEs can be

```
CLIPS Basic Programming Guide 51
```

satisfied by more than one group of pattern entities. In order to cause the reevaluation of a test CE,
a pattern entity matching a CE prior to the test CE must be changed.

Example 1

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
(slot age))
CLIPS>
(defrule older
(person (name ?name1) (age ?age1))
(person (name ?name2) (age ?age2))
(test (> ?age1 ?age2))
=>
(println ?name1 " is older than " ?name2))
CLIPS> (assert (person (name "John Smith") (age 15)))
<Fact-1>
CLIPS> (assert (person (name "Jane Farmer") (age 23)))
<Fact-2>
CLIPS> (assert (person (name "Jake Jones") (age 37)))
<Fact-3>
CLIPS> (run)
Jake Jones is older than Jane Farmer
Jake Jones is older than John Smith
Jane Farmer is older than John Smith
CLIPS>
```

Example 2

```
CLIPS> (clear)
CLIPS>
(defrule at-least- 3 - items
(grocery-list $?list)
(test (>= (length$ ?list) 3))
=>)
CLIPS> (assert (grocery-list apple pears))
<Fact-1>
CLIPS> (assert (grocery-list milk eggs cheese))
<Fact-2>
CLIPS> (assert (grocery-list bread onions tomatoes cheese))
<Fact-3>
CLIPS> (agenda)
0 at-least- 3 - items: f- 3
0 at-least- 3 - items: f- 2
For a total of 2 activations.
CLIPS>
```

```
52 Section 5: Defrule Construct
```

#### 5.4.3 Or Conditional Element

The or conditional element allows any one of several conditional elements to activate a rule. If
any of the conditional elements inside of the or CE is satisfied, then the or CE is satisfied. If all
other LHS conditional elements are satisfied, the rule will be activated. Note that a rule will be
activated for each conditional element with an or CE that is satisfied (assuming the other
conditional elements of the rule are also satisfied). Any number of conditional elements may
appear within an or CE. The or CE produces the identical effect of writing several rules with
similar LHS’s and RHS’s.

Syntax

```
<or-CE> ::= (or <conditional-element>+)
```

Again, if more than one of the conditional elements in the or CE can be met, the rule will fire
multiple times, once for each satisfied combination of conditions.

Example

```
CLIPS> (clear)
CLIPS>
(defrule system-fault
(error-status unknown)
(or (temp high)
(valve broken)
(pump off))
=>
(println "The system has a fault."))
CLIPS> (assert (error-status unknown))
<Fact-1>
CLIPS> (assert (temp high))
<Fact-2>
CLIPS> (assert (pump off))
<Fact-3>
CLIPS> (agenda)
0 system-fault: f-1,f- 3
0 system-fault: f-1,f- 2
For a total of 2 activations.
CLIPS> (run)
The system has a fault.
The system has a fault.
CLIPS>
```

Note that the above example is exactly equivalent to the following three (separate) rules:

```
(defrule system-fault
(error-status unknown)
(temp high)
=>
(println "The system has a fault."))
```

```
CLIPS Basic Programming Guide 53
```

```
(defrule system-fault
(error-status unknown)
(valve broken)
=>
(println "The system has a fault."))
```

```
(defrule system-fault
(error-status unknown)
(pump off)
=>
(println "The system has a fault."))
```

#### 5.4.4 And Conditional Element

CLIPS assumes that all rules have an implicit and conditional element surrounding the
conditional elements on the LHS. This means that all conditional elements on the LHS must be
satisfied before the rule can be activated. An explicit and conditional element is provided to allow
the mixing of and CEs and or CEs. This allows other types of conditional elements to be grouped
together within or and not CEs. The and CE is satisfied if all of the CEs inside of the explicit and
CE are satisfied. If all other LHS conditions are true, the rule will be activated. Any number of
conditional elements may be placed within an and CE. Note that the LHS of any rule is enclosed
within an implied and CE.

Syntax

```
<and-CE> ::= (and <conditional-element>+)
```

Example

```
CLIPS> (clear)
CLIPS>
(defrule system-flow
(error-status confirmed)
(or (and (temp high)
(valve closed))
(and (temp low)
(valve open)))
=>
(println "The system is having a flow problem."))
CLIPS> (assert (error-status confirmed))
<Fact-1>
CLIPS> (assert (temp high))
<Fact-2>
CLIPS> (assert (valve closed))
<Fact-3>
CLIPS> (agenda)
0 system-flow: f-1,f-2,f- 3
For a total of 1 activation.
CLIPS>
```

```
54 Section 5: Defrule Construct
```

#### 5.4.5 Not Conditional Element

Sometimes the lack of information is meaningful; i.e., one wishes to fire a rule if a pattern entity
or other CE does not exist. The not conditional element provides this capability. The not CE is
satisfied only if the conditional element contained within it is not satisfied. As with other
conditional elements, any number of additional CEs may be on the LHS of the rule and field con-
straints may be used within the negated pattern.

Syntax

```
<not-CE> ::= (not <conditional-element>)
```

Only one CE may be negated at a time. Multiple patterns may be negated by using multiple not
CEs. The same holds true for variable bindings within a not CE. Previously bound variables may
be used freely inside of a not CE. However, variables bound for the first time within a not CE can
be used only in that pattern.

Example 1

```
CLIPS> (clear)
CLIPS>
(defrule no-milk
(not (grocery-list $? milk $?))
=>
(println "No grocery list contains milk"))
CLIPS> (assert (grocery-list bread turkey cheese))
<Fact-1>
CLIPS> (assert (grocery-list chips salsa))
<Fact-2>
CLIPS> (agenda)
0 no-milk: *
For a total of 1 activation.
CLIPS> (assert (grocery-list flour eggs milk))
<Fact-3>
CLIPS> (agenda)
CLIPS>
```

Example 2

```
CLIPS> (clear)
CLIPS>
(defrule highest-number
(number ?n)
(not (number ?n2&:(> ?n2 ?n)))
=>
(println "Highest number is " ?n))
CLIPS> (assert (number 3))
<Fact-1>
CLIPS> (assert (number 15))
<Fact-2>
CLIPS> (assert (number 7))
```

```
CLIPS Basic Programming Guide 55
```

```
<Fact-3>
CLIPS> (agenda)
0 highest-number: f-2,*
For a total of 1 activation.
CLIPS> (run)
Highest number is 15
CLIPS>
```

Example 3

```
CLIPS> (clear)
CLIPS>
(defrule check-valve
(check-status ?valve)
(not (valve-broken ?valve))
=>
(println "Valve " ?valve " is OK"))
CLIPS>
(assert (check-status v1)
(check-status v2)
(check-status v3)
(check-status v4))
<Fact-4>
CLIPS>
(assert (valve-broken v2)
(valve-broken v4))
<Fact-6>
CLIPS> (run)
Valve v3 is OK
Valve v1 is OK
CLIPS>
```

Example 4

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
(slot age))
CLIPS>
(defrule oldest
(person (name ?name1) (age ?age1))
(not (person (age ?age2&:(> ?age2 ?age1))))
=>
(println ?name1 " is the oldest person"))
CLIPS> (assert (person (name "John Smith") (age 20)))
<Fact-1>
CLIPS> (assert (person (name "Sally Jones") (age 18)))
<Fact-2>
CLIPS> (assert (person (name "Bill White") (age 14)))
<Fact-3>
CLIPS> (agenda)
0 oldest: f-1,*
For a total of 1 activation.
```

```
56 Section 5: Defrule Construct
```

```
CLIPS> (run)
John Smith is the oldest person
CLIPS>
```

#### 5.4.6 Exists Conditional Element.......................................................................................

The exists conditional element provides a mechanism for determining if a group of specified CEs
is satisfied by a least one set of pattern entities.

Syntax

```
<exists-CE> ::= (exists <conditional-element>+)
```

The exists CE is implemented by replacing the exists keyword with two nested not CEs. For
example, the following rule

```
(defrule example
(exists (a ?x) (b ?x))
=>)
```

is equivalent to the rule below

```
(defrule example
(not (not (and (a ?x) (b ?x))))
=>)
```

Because of the way the exists CE is implemented using not CEs, the restrictions which apply to
CEs found within not CEs (such as binding a pattern CE to a fact-address) also apply to the CEs
found within an exists CE.

Example 1

```
CLIPS> (clear)
CLIPS>
(deftemplate hero
(slot name)
(slot status (default unoccupied)))
CLIPS> (assert (goal save-the-day))
<Fact-1>
CLIPS> (assert (hero (name "Death Defying Man")))
<Fact-2>
CLIPS> (assert (hero (name "Stupendous Man")))
<Fact-3>
CLIPS> (assert (hero (name "Incredible Woman")))
<Fact-4>
CLIPS>
(defrule save-the-day
(goal save-the-day)
(exists (hero (status unoccupied)))
```

```
CLIPS Basic Programming Guide 57
```

```
=>
(println "The day is saved"))
CLIPS> (agenda)
0 save-the-day: f-1,*
For a total of 1 activation.
CLIPS> (matches save-the-day)
Matches for Pattern 1
f- 1
Matches for Pattern 2
f- 2
f- 3
f- 4
Partial matches for CEs 1 - 2
f-1,*
Activations
f-1,*
(4 1 1)
CLIPS> (run)
The day is saved
CLIPS>
```

Example 2

```
CLIPS> (clear)
CLIPS>
(defrule system-fault
(error-status unknown)
(exists (or (temp high)
(valve broken)
(pump off)))
=>
(println "The system has a fault."))
CLIPS> (assert (error-status unknown))
<Fact-1>
CLIPS> (assert (temp high))
<Fact-2>
CLIPS> (assert (pump off))
<Fact-3>
CLIPS> (agenda)
0 system-fault: f-1,*
For a total of 1 activation.
CLIPS> (run)
The system has a fault.
CLIPS>
```

Example 3

```
CLIPS> (clear)
CLIPS>
(defrule valve-broken
(exists (check-status ?valve)
(valve-broken ?valve))
=>
(println "There is a broken valve"))
```

```
58 Section 5: Defrule Construct
```

```
CLIPS>
(assert (check-status v1)
(check-status v2)
(check-status v3)
(check-status v4))
<Fact-4>
CLIPS>
(assert (valve-broken v2)
(valve-broken v4))
<Fact-6>
CLIPS> (agenda)
0 valve-broken: *
For a total of 1 activation.
CLIPS> (run)
There is a broken valve
CLIPS>
```

#### 5.4.7 Forall Conditional Element

The forall conditional element provides a mechanism for determining if a group of specified CEs
is satisfied for every occurence of another specified CE.

Syntax

```
<forall-CE> ::= (forall <conditional-element>
<conditional-element>+)
```

The forall CE is implemented by replacing the forall keyword with combinations of not and and
CEs. For example, the following rule

```
(defrule example
(forall (a ?x) (b ?x) (c ?x))
=>)
```

is equivalent to the rule below

```
(defrule example
(not (and (a ?x)
(not (and (b ?x) (c ?x)))))
=>)
```

Because of the way the forall CE is implemented using not CEs, the restrictions which apply to
CE found within not CEs (such as binding a pattern CE to a fact-address) also apply to the CEs
found within an forall CE.

Example

The following rule determines if every student has passed in reading, writing, and arithmetic by
using the forall CE.

```
CLIPS Basic Programming Guide 59
```

```
CLIPS> (clear)
CLIPS>
(deftemplate student
(slot name))
CLIPS>
(deftemplate passed
(slot name)
(slot subject))
CLIPS>
(defrule all-students-passed
(forall
(student (name ?name))
(passed (name ?name) (subject reading))
(passed (name ?name) (subject writing))
(passed (name ?name) (subject arithmetic)))
=>
(println "All students passed."))
CLIPS>
```

The following commands illustrate how the forall CE works in the all-students-passed rule. Note
that initially the all-students-passed rule is satisfied because there are no students.

```
CLIPS> (agenda)
0 all-students-passed: *
For a total of 1 activation.
CLIPS>
```

After the (student Bob) fact is asserted, the rule is no longer satisfied since Bob has not passed
reading, writing, and arithmetic.

```
CLIPS> (assert (student (name Bob)))
<Fact-1>
CLIPS> (agenda)
CLIPS>
```

The rule is still not satisfied after Bob has passed reading and writing, since he still has not passed
arithmetic.

```
CLIPS> (assert (passed (name Bob) (subject reading)))
<Fact-2>
CLIPS> (assert (passed (name Bob) (subject writing)))
<Fact-3>
CLIPS> (agenda)
CLIPS>
```

Once Bob has passed arithmetic, the all-students-passed rule is reactivated.

```
60 Section 5: Defrule Construct
```

```
CLIPS> (assert (passed (name Bob) (subject arithmetic)))
<Fact-4>
CLIPS> (agenda)
0 all-students-passed: *
For a total of 1 activation.
CLIPS>
```

If a new student is asserted, then the rule is taken off the agenda, since John has not passed reading,
writing, and arithmetic.

```
CLIPS> (assert (student (name John)))
<Fact-5>
CLIPS> (agenda)
CLIPS> (matches all-students-passed)
Matches for Pattern 1
f- 1
f- 5
Matches for Pattern 2
f- 2
Matches for Pattern 3
f- 3
Matches for Pattern 4
f- 4
Partial matches for CEs 1 - 2
f-1,f- 2
Partial matches for CEs 1 - 3
f-1,f-2,f- 3
Partial matches for CEs 1 - 4
f-1,f-2,f-3,f- 4
Partial matches for CEs 1 (P1) , 2 (P2 - P4)
f-5,*
Partial matches for CEs 1 (P1 - P4)
None
Activations
None
(5 4 0)
CLIPS>
```

Removing both student facts reactivates the rule again.

```
CLIPS> (retract 1 5)
CLIPS> (agenda)
0 all-students-passed: *
For a total of 1 activation.
CLIPS>
```

#### 5.4.8 Logical Conditional Element

The logical conditional element provides a truth maintenance capability for pattern entities
(facts or instances) created by rules that use the logical CE. A pattern entity created on the RHS
(or as a result of actions performed from the RHS) can be made logically dependent upon the

```
CLIPS Basic Programming Guide 61
```

pattern entities that matched the patterns enclosed with the logical CE on the LHS of the rule. The
pattern entities matching the LHS logical patterns provide logical support to the facts and instance
created by the RHS of the rule. A pattern entity can be logically supported by more than one group
of pattern entities from the same or different rules. If any one supporting pattern entities is removed
from a group of supporting pattern entities (and there are no other supporting groups), then the
pattern entity is removed.

If a pattern entity is created without logical support (e.g., from a deffacts, definstaces, as a top-level
command, or from a rule without any logical patterns), then the pattern entity has unconditional
support. Unconditionally supporting a pattern entity removes all logical support (without causing
the removal of the pattern entity). In addition, further logical support for an unconditionally
supported pattern entity is ignored. Removing a rule that generated logical support for a pattern
entity, removes the logical support generated by that rule (but does not cause the removal of the
pattern entity if no logical support remains).

Syntax

```
<logical-CE> ::= (logical <conditional-element>+)
```

The logical CE groups patterns together exactly as the explicit and CE does. It may be used in
conjunction with the and, or, and not CEs. However, only the first N patterns of a rule can have
the logical CE applied to them. For example, the following rule is legal.

```
(defrule ok
(logical (credit-score ?person good))
(logical (debt-and-income ?person good))
?f <- (assessing-loan)
=>
(retract ?f)
(assert (loan-approved ?person)))
```

Whereas the following rules are illegal.

```
(defrule not-ok- 1
(logical (credit-score ?person good))
?f <- (assessing-loan)
(logical (debt-and-income ?person good))
=>
(assert (loan-approved ?person)))
```

```
(defrule not-ok- 2
?f <- (assessing-loan)
(logical (credit-score ?person good))
(logical (debt-and-income ?person good))
=>
(assert (loan-approved ?person)))
```

```
(defrule not-ok- 3
```

```
62 Section 5: Defrule Construct
```

```
(or (credit-score-waver ?person)
(logical (credit-score ?person good)))
(logical (debt-and-income ?person good))
?f <- (assessing-loan)
=>
(retract ?f)
(assert (loan-approved ?person)))
```

Example 1

```
This example demonstrates facts receiving support from multiple rules.
```

```
CLIPS> (clear)
CLIPS>
(defrule good-scores
(logical (credit-score good))
(logical (debt-and-income good))
(assessing-loan)
=>
(assert (loan-assessed))
(assert (loan-approved)))
CLIPS>
(defrule wavers
(logical (credit-score-waver))
(logical (debt-and-income-waver))
(assessing-loan)
=>
(assert (loan-assessed))
(assert (loan-approved)))
CLIPS>
(assert (credit-score good)
(debt-and-income good)
(assessing-loan)
(credit-score-waver)
(debt-and-income-waver))
<Fact-5>
CLIPS> (facts)
f-1 (credit-score good)
f-2 (debt-and-income good)
f-3 (assessing-loan)
f-4 (credit-score-waver)
f-5 (debt-and-income-waver)
For a total of 5 facts.
CLIPS> (agenda)
0 wavers: f-4,f-5,f- 3
0 good-scores: f-1,f-2,f- 3
For a total of 2 activations.
CLIPS>
```

```
CLIPS Basic Programming Guide 63
```

```
The wavers rule executes asserting and providing logical support for the loan-assessed and
loan-approved facts. The good-scores rule executes next asserting the same two facts which
adds additional logical support.
```

```
CLIPS> (watch rules)
CLIPS> (watch facts)
CLIPS> (run)
FIRE 1 wavers: f-4,f-5,f- 3
==> f-6 (loan-assessed)
==> f-7 (loan-approved)
FIRE 2 good-scores: f-1,f-2,f- 3
CLIPS>
```

```
Retracting the credit-score fact removes the logical support for the loan-assessed and loan-
approved facts asserted by the good-scores rule. The logical support provided by the wavers
rule still exists, so these facts are not retracted.
```

```
CLIPS> (retract 1)
<== f-1 (credit-score good)
CLIPS>
```

```
Asserting the loan-approved fact without the restrictions of a logical conditional element
gives it unconditional support.
```

```
CLIPS> (assert (loan-approved))
<Fact-7>
CLIPS>
```

```
Retracting the credit-score-waver fact removes the remaining logical support for the loan-
assessed and loan-approved facts provided by the wavers rule. This causes the loan-
assessed fact to be retracted since it has no remaining logical support, but the loan-approved
fact is not retracted since it is now unconditionally supported.
```

```
CLIPS> (retract 4)
<== f-4 (credit-score-waver)
<== f-6 (loan-assessed)
CLIPS> (unwatch all)
CLIPS>
```

Example 2

```
The logical CE can be used with an object pattern to create pattern entities that are logically
dependent on changes to specific slots in the matching instance(s) rather than all slots. This
cannot be accomplished with template facts because a change to a template fact slot actually
involves the retraction of the old template fact and the assertion of a new one, whereas a
change to an instance slot is done in place. The example below illustrates this behavior:
```

```
CLIPS> (clear)
CLIPS>
```

```
64 Section 5: Defrule Construct
```

```
(defclass PERSON (is-a USER)
(slot full-name)
(slot age)
(slot credit-score))
CLIPS>
(deftemplate person
(slot full-name)
(slot age)
(slot credit-score))
CLIPS>
(defrule credit-check-instance
(logical (object (is-a PERSON)
(full-name ?name)
(credit-score ?cs&:(< ?cs 580))))
=>
(assert (reject-loan ?name)))
CLIPS>
(defrule credit-check-fact
(logical (person (full-name ?name)
(credit-score ?cs&:(< ?cs 580))))
=>
(assert (reject-loan ?name)))
CLIPS>
(make-instance p1 of PERSON
(full-name "Jack Jones")
(age 37)
(credit-score 500))
[p1]
CLIPS>
(assert (person (full-name "Sally Smith")
(age 37)
(credit-score 500)))
<Fact-1>
CLIPS> (watch facts)
CLIPS> (run)
==> f-2 (reject-loan "Sally Smith")
==> f-3 (reject-loan "Jack Jones")
CLIPS> (send [p1] put-age 38)
38
CLIPS> (modify 1 (age 38))
<== f-1 (person ... (age 37) ...)
<== f-2 (reject-loan "Sally Smith")
==> f-1 (person ... (age 38) ...)
<Fact-1>
CLIPS> (agenda)
0 credit-check-fact: f- 1
For a total of 1 activation.
CLIPS> (unwatch facts)
CLIPS>
```

Example 3

```
CLIPS> (clear)
CLIPS> (unwatch all)
CLIPS>
```

CLIPS Basic Programming Guide 65

```
(defrule down-payment-percent
(logical (loan-amount ?la)
(available-down-payment ?adp))
=>
(bind ?dpp (/ ?adp ?la))
(assert (down-payment-percent ?dpp)))
CLIPS>
(defrule monthly-debt-percent
(logical (monthly-house-payment ?mhp)
(other-monthly-debt ?omd)
(gross-monthly-income ?gmi))
=>
(bind ?mdp (/ (+ ?mhp ?omd) ?gmi))
(assert (monthly-debt-percent ?mdp)))
CLIPS>
(defrule approved
(logical (credit-score ?cs&:(>= ?cs 720))
(down-payment-percent ?dpp&:(>= ?dpp 0.20))
(monthly-debt-percent ?mdp&:(<= ?mdp 0.36)))
=>
(assert (loan-approved)))
CLIPS> (assert (loan-amount 100000))
<Fact-1>
CLIPS> (assert (available-down-payment 25000))
<Fact-2>
CLIPS> (assert (monthly-house-payment 1000))
<Fact-3>
CLIPS> (assert (other-monthly-debt 800))
<Fact-4>
CLIPS> (assert (gross-monthly-income 6000))
<Fact-5>
CLIPS> (assert (credit-score 800))
<Fact-6>
CLIPS> (agenda)
0 monthly-debt-percent: f-3,f-4,f- 5
0 down-payment-percent: f-1,f- 2
For a total of 2 activations.
CLIPS> (watch rules)
CLIPS> (watch facts)
CLIPS> (run)
FIRE 1 monthly-debt-percent: f-3,f-4,f- 5
==> f-7 (monthly-debt-percent 0.3)
FIRE 2 down-payment-percent: f-1,f- 2
==> f-8 (down-payment-percent 0.25)
FIRE 3 approved: f-6,f-8,f- 7
==> f-9 (loan-approved)
CLIPS> (retract 2)
<== f-2 (available-down-payment 25000)
<== f-8 (down-payment-percent 0.25)
<== f-9 (loan-approved)
CLIPS> (assert (available-down-payment 15000))
==> f-10 (available-down-payment 15000)
<Fact-10>
CLIPS> (run)
FIRE 1 down-payment-percent: f-1,f- 10
```

```
66 Section 5: Defrule Construct
```

```
==> f-11 (down-payment-percent 0.15)
CLIPS>
```

#### 5.4.9 Automatic Replacement of LHS CEs

Under certain circumstances, CLIPS will change the CEs specified in the rule LHS.

5.4.9. 1 Or CEs Following Not CEs

If an or CE immediately follows a not CE, then the not/or CE combination is replaced with an
and/not CE combination where each of the CEs contained in the original or CE is enclosed within
a not CE and then all of the not CEs are enclosed within a single and CE. For example, the
following rule

```
(defrule example
(a ?x)
(not (or (b ?x)
(c ?x)))
=>)
```

would be changed as follows.

```
(defrule example
(a ?x)
(and (not (b ?x))
(not (c ?x)))
=>)
```

#### 5.4.10 Declaring Rule Properties

This feature allows the properties or characteristics of a rule to be defined. The characteristics are
declared on the LHS of a rule using the declare keyword. A rule may only have one declare
statement and it must appear before the first conditional element on the LHS.

Syntax

```
<declaration> ::= (declare <rule-property>+)
```

```
<rule-property> ::= (salience <integer-expression>) |
(auto-focus <boolean-symbol>)
```

```
<boolean-symbol> ::= TRUE | FALSE
```

```
CLIPS Basic Programming Guide 67
```

5.4.10.1 The Salience Rule Property

The salience rule property allows the user to assign a priority to a rule. When multiple rules are in
the agenda, the rule with the highest priority will fire first. The declared salience value should be
an expression that evaluates to an an integer in the range -10000 to +10000. Salience expressions
may freely reference global variables and other functions (however, you should avoid using
functions with side-effects). If unspecified, the salience value for a rule defaults to zero.

Example

```
CLIPS> (clear)
CLIPS> (defglobal ?*s1* = -10)
CLIPS> (deffunction s2 () 50)
CLIPS>
(defrule r1
=>)
CLIPS>
(defrule r2
(declare (salience 20))
=>)
CLIPS>
(defrule r3
(declare (salience (s2)))
=>)
CLIPS>
(defrule r4
(declare (salience ?*s1*))
=>)
CLIPS>
(defrule r5
(declare (salience (+ ?*s1* (s2))))
=>)
CLIPS> (agenda)
50 r3: *
40 r5: *
20 r2: *
0 r1: *
```

- 10 r4: \*
  For a total of 5 activations.
  CLIPS>

Salience values can be evaluated at one of three times: when a rule is defined, when a rule is
activated, and every cycle of execution (the latter two situations are referred to as dynamic
salience). By default, salience values are only evaluated when a rule is defined. The
set-salience-evaluation command can be used to change this behavior. Note that each salience
evaluation method encompasses the previous method (i.e. if saliences are evaluated every cycle,
then they are also evaluated when rules are activated or defined).

```
68 Section 5: Defrule Construct
```

❖ Usage Note

Despite the large number of possible values, with good design there’s rarely a need for more than
five salience values in a simple program and ten salience values in a complex program. Defining
the salience values as global variables allows you to specify and document the values used by your
program in a centralized location and also makes it easier to change the salience of a group of rules
sharing the same salience value:

```
(defglobal ?*high-priority* = 100)
```

```
(defglobal ?*low-priority* = -100)
```

```
(defrule rule- 1
(declare (salience ?*high-priority*))
=>)
```

```
(defrule rule- 2
(declare (salience ?*low-priority*))
=>)
```

5.4.10.2 The Auto-Focus Rule Property

The auto-focus rule property allows an automatic focus command to be executed whenever a rule
becomes activated. If the auto-focus property for a rule is TRUE, then a focus command on the
module in which the rule is defined is automatically executed whenever the rule is activated. If the
auto-focus property for a rule is FALSE, then no action is taken when the rule is activated. If
unspecified, the auto-focus value for a rule defaults to FALSE.

Example

```
CLIPS> (clear)
CLIPS> (defmodule MAIN (export ?ALL))
CLIPS>
(deftemplate person
(slot name)
(slot age))
CLIPS>
(defrule get-person
=>
(print "What is your name? ")
(bind ?name (readline))
(print "What is your age? ")
(bind ?age (read))
(assert (person (name ?name) (age ?age))))
CLIPS> (defmodule VIOLATIONS (import MAIN ?ALL))
CLIPS>
(defrule bad-age
(declare (auto-focus TRUE))
(person (name ?name) (age ?age&:(< ?age 0)))
=>
```

CLIPS Basic Programming Guide 69

```
(println ?name " has a bad age value."))
CLIPS> (reset)
CLIPS> (watch focus)
CLIPS> (watch rules)
CLIPS> (run)
FIRE 1 get-person: *
What is your name? Sam Jones
What is your age? - 9
==> Focus VIOLATIONS from MAIN
FIRE 2 bad-age: f- 1
Sam Jones has a bad age value.
<== Focus VIOLATIONS to MAIN
<== Focus MAIN
CLIPS> (unwatch all)
CLIPS>
```

```
70 Section 6: Defglobal Construct
```

## Section 6: Defglobal Construct

With the defglobal construct, global variables can be defined, set, and accessed within the CLIPS
environment. Global variables can be accessed as part of the pattern-matching process, but
changing them does not invoke the pattern-matching process. The bind function is used to set the
value of global variables. Global variables are reset to their original value when the reset command
is performed or when bind is called for the global with no values. This behavior can be changed
using the set-reset-globals function. Global variables can be removed by using the clear command
or the undefglobal command. If the globals item is being watched as a result of the watch
command, then an informational message will be displayed each time the value of a global variable
is changed.

Syntax

```
(defglobal [<defmodule-name>] <global-assignment>*)
```

```
<global-assignment> ::= <global-variable> = <expression>
```

```
<global-variable> ::= ?*<symbol>*
```

There may be multiple defglobal constructs and any number of global variables may be defined in
each defglobal statement. The optional <defmodule-name> indicates the module in which the
defglobals will be defined. If none is specified, the globals will be placed in the current module. If
a variable was defined in a previous defglobal construct, its value will be replaced by the value
found in the new defglobal construct. If an error is encountered when defining a defglobal
construct, any global variable definitions that occurred before the error was encountered will still
remain in effect.

Commands that operate on defglobals such as ppdefglobal and undefglobal expect the symbolic
name of the global without the astericks (e.g. use the symbol max when you want to refer to the
global variable ?_max_).

Global variables may be used anyplace that a local variable could be used (with two exceptions).
Global variables may not be used as a parameter variable for a deffunction, defmethod, or message-
handler. Global variables may not be used in the same way that a local variable is used on the LHS
of a rule to bind a value. Therefore, the following rule is illegal

```
(defrule example
(number ?*x*)
=>)
```

```
CLIPS Basic Programming Guide 71
```

The following rule, however, is legal.

```
(defrule example
(number ?y&:(> ?y ?*x*))
=>)
```

Note that this rule will not necessarily be updated when the value of ?_x_ is changed. For example,
if ?_x_ is 4 and the fact (number 3) is added, then the rule is not satisfied. If the value of ?_x_ is
now changed to 2, the rule will not be activated.

Example

```
(defglobal
?*x* = 3
?*y* = ?*x*
?*z* = (+ ?*x* ?*y*)
?*q* = (create$ a b c))
```

❖ Usage Note

The inappropriate use of globals within rules is quite often the first resort of beginning
programmers who have reached an impasse in developing a program because they do not fully
understand how rules and pattern-matching work. As it relates to this issue, the following sentence
from the beginning of this section is important enough to repeat:

Global variables can be accessed as part of the pattern-matching process, but changing them does
not invoke the pattern-matching process.

Facts and instances are the primary mechanism that should be used to pass information from one
rule to another specifically because they do invoke pattern-matching. A change to a slot value of
a fact or instance will trigger pattern-matching ensuring that a rule is aware of the current state of
that fact or instance. Since a change to a global variable does not trigger pattern-matching, it is
possible for a rule to remain activated based on a past value of a global variable and that is
undesirable in most situations.

It’s worth pointing out that facts and instances are no less ‘global’ in nature than global variables.
Just as a rule can access any global variable that’s visible (i.e. it hasn’t been hidden through the
use of modules), so too can it access any fact or instance belonging to a deftemplate or defclass
that’s visible. In the case of a fact, one can either pattern-match for the fact on the LHS of a rule
or use the fact-set query functions from the RHS of a rule. In the case of an instance, pattern-
matching and instance-set query functions can also be used, and in addition an instance can be
directly referenced by name just as a global variable can.

```
72 Section 6: Defglobal Construct
```

Common Problem

One of the more common situations in which it is tempting to use global variables is collecting a
group of slot values from a fact. First attempts at rules to accomplish this task often loop endlessly
because of rules inadvertently retriggered by changes. For example, the following rule will loop
endlessly because the new collection fact asserted will create an activation with the same data fact
that was just added to the collection fact:

```
(defrule add-data
(data ?data)
?c <- (collection $?collection)
=>
(retract ?c)
(assert (collection ?collection ?data)))
```

This problem can be corrected by removing the data fact just added to the collection fact:

```
(defrule add-data
?f <- (data ?data)
?c <- (collection $?collection)
=>
(retract ?f ?c)
(assert (collection ?collection ?data)))
```

Retracting the data facts, however, isn’t a viable solution if these facts are needed by other rules.
A non-destructive approach makes use of temporary facts created by a helper rule:

```
(defrule add-data-helper
(data ?data)
=>
(assert (temp-data ?data)))
```

```
(defrule add-data
?f <- (temp-data ?data)
?c <- (collection $?collection)
=>
(retract ?f ?c)
(assert (collection ?collection ?data)))
```

It certainly looks simpler, however, to use a global variable to collect the slot values:

```
(defglobal ?*collection* = (create$))
```

```
(defrule add-data
(data ?data)
=>
(bind ?*collection* (create$ ?*collection* ?data)))
```

Again, the drawback to this approach is that changes to a global variable do not trigger
pattern-matching, so in spite of its greater complexity the fact-based approach is still preferable.

```
CLIPS Basic Programming Guide 73
```

Although it’s important to understand how each of the previous approaches work, they’re not
practical solutions. If there are 1000 data facts, the add-data/add-add-helper rules will each fire
1000 times generating and retracting 2000 facts. The best solution is to use the fact-set query
functions to iterate over all of the data facts and generate the collection fact as the result of a single
rule firing:

```
(defrule collect-data
(collect-data)
=>
(bind ?data (create$))
(do-for-all-facts ((?f data)) TRUE
(bind ?data (create$ ?data ?f:implied)))
(assert (collection ?data)))
```

With this approach, the collection fact is available for pattern-matching with the added benefit that
there are no intermediate results generated in creating the fact. Typically if other rules are waiting
for the finished result of the collection, they would need to have lower salience so that they aren’t
fired for the intermediate results:

```
(defrule print-data
(declare (salience -10))
(collection $?data)
=>
(println "The collected data is " ?data))
```

If the data facts are collected by a single rule firing, then the salience declaration is unnecessary.

Appropriate Uses

The primary use of global variables (in conjunction with rules) is in making a program easier to
maintain. It is a rare situation where a global variable is required in order to solve a problem. One
appropriate use of global variables is defining salience values shared among multiple rules:

```
(defglobal ?*high-priority* = 100)
```

```
(defrule rule- 1
(declare (salience ?*high-priority*))
=>)
```

```
(defrule rule- 2
(declare (salience ?*high-priority*))
=>)
```

Another use is defining constants used on the LHS or RHS of a rule:

```
(defglobal ?*week-days* =
(create$ monday tuesday wednesday thursday friday saturday sunday))
```

```
74 Section 6: Defglobal Construct
```

```
(defrule invalid-day
(day ?day&:(not (member$ ?day ?*week-days*)))
=>
(println ?day " is invalid"))
```

```
(defrule valid-day
(day ?day&:(member$ ?day ?*week-days*))
=>
(println t ?day " is valid"))
```

A third use is passing information to a rule when it is desirable not to trigger pattern-matching. In
the following rule, a global variable is used to determine whether additional debugging information
is printed:

```
(defglobal ?*debug-print* = nil)
```

```
(defrule rule-debug
?f <- (info ?info)
=>
(retract ?f)
(printout ?*debug-print* "Retracting info " ?info crlf))
```

If ?_debug-print_ is set to nil, then the printout statement will not display any information. If the
?_debug-print_ is set to t, then debugging information will be sent to the screen. Because ?_debug-
print_ is a global, it can be changed interactively without causing rules to be reactivated. This is
useful when stepping through a program because it allows the level of information displayed to be
changed without effecting the normal flow of the program.

It’s possible, but a little more verbose, to achieve this same functionality using instances rather
than global variables:

```
(defclass DEBUG-INFO
(is-a USER)
(slot debug-print))
```

```
(definstances debug
([debug-info] of DEBUG-INFO (debug-print nil)))
```

```
(defrule rule-debug
?f <- (info ?info)
=>
(retract ?f)
(printout (send [debug-info] get-debug-print) "Retracting info " ?info crlf))
```

Unlike fact slots, changes to a slot of an instance won’t trigger pattern matching in a rule unless
the slot is specified on the LHS of that rule, thus you have explicit control over whether an instance
slot triggers pattern-matching. The following rule won’t be retriggered if a change is made to the
debug-print slot:

```
CLIPS Basic Programming Guide 75
```

```
(defrule rule-debug
?f <- (info ?info)
(object (is-a DEBUG-INFO) (name ?name))
=>
(retract ?f)
(printout (send ?name get-debug-print) "Retracting info " ?info crlf))
```

This is a generally applicable technique and can be used in many situations to prevent rules from
inadvertently looping when slot values are changed.

```
76 Section 7: Deffunction Construct
```

## Section 7: Deffunction Construct

With the deffunction construct, new functions may be defined directly in CLIPS. Deffunctions
are equivalent in use to other functions. The only differences between user-defined external
functions and deffunctions are that deffunctions are written in CLIPS and executed by CLIPS
interpretively and user-defined external functions are written in an external language, such as C,
and executed by CLIPS directly. Thus deffunctions allow the addition of new functions without
having to recompile and relink CLIPS.

A deffunction is comprised of five elements: 1) a name, 2) an optional comment, 3) a list of zero
or more required parameters, 4) an optional wildcard parameter to handle a variable number of
arguments and 5) a sequence of actions, or expressions, which will be executed in order when the
deffunction is called.

Syntax

```
(deffunction <name> [<comment>]
(<regular-parameter>* [<wildcard-parameter>])
<action>*)
```

```
<regular-parameter> ::= <single-field-variable>
<wildcard-parameter> ::= <multifield-variable>
```

A deffunction must have a unique name different from all other system functions and generic
functions. In particular, a deffunction cannot be overloaded like a system function. A deffunction
must be declared prior to being called from another deffunction, generic function method, object
message-handler, rule, or the REPL. The only exception is a self recursive deffunction.

A deffunction may accept exactly or at least a specified number of arguments, depending on
whether a wildcard parameter is used or not. The regular parameters specify the minimum number
of arguments that must be passed to the deffunction. Each of these parameters may be referenced
like a normal single-field variable within the actions of the deffunction. If a wildcard parameter is
present, the deffunction may be passed any number of arguments greater than or equal to the
minimum. If no wildcard parameter is present, then the deffunction must be passed exactly the
number of arguments specified by the regular parameters. All arguments to a deffunction that do
not correspond to a regular parameter are grouped into a multifield value that can be referenced by
the wildcard parameter. The standard CLIPS multifield functions, such as length$ and nth$, can
be applied to the wildcard parameter.

```
CLIPS Basic Programming Guide 77
```

Example

```
CLIPS> (clear)
CLIPS>
(deffunction print-args (?a ?b $?c)
(println ?a " " ?b " and " (length$ ?c) " extras: " ?c))
CLIPS> (print-args 1 2)
1 2 and 0 extras: ()
CLIPS> (print-args a b c d)
a b and 2 extras: (c d)
CLIPS>
```

When a deffunction is called, its actions are executed in order. The return value of a deffunction
is the evaluation of the last action. If a deffunction has no actions, its return value is the symbol
FALSE. If an error occurs while the deffunction is executing, any actions not yet executed will be
aborted, and the deffunction will return the symbol FALSE.

Deffunctions may be self and mutually recursive. Self recursion is accomplished simply by calling
the deffunction from within its own actions.

Example

```
CLIPS> (clear)
CLIPS>
(deffunction factorial (?a)
(if (or (not (integerp ?a)) (< ?a 0))
then
(println "Factorial Error!")
else
(if (= ?a 0)
then 1
else (* ?a (factorial (- ?a 1))))))
CLIPS> (factorial 1)
1
CLIPS> (factorial 2)
2
CLIPS> (factorial 3)
6
CLIPS>
```

Mutual recursion between two deffunctions requires a forward declaration of one of the
deffunctions. A forward declaration is simply a declaration of the deffunction without any actions.
In the following example, the deffunction is-odd is forward declared so that it may be called by
the deffunction is-even. Then the deffunction is-odd is redefined with actions that call the
deffunction is-even.

```
78 Section 7: Deffunction Construct
```

Example

```
CLIPS> (deffunction is-odd (?n))
CLIPS>
(deffunction is-even (?n)
(if (= ?n 0)
then TRUE
else (is-odd (- (abs ?n) 1))))
CLIPS>
(deffunction is-odd (?n)
(if (= ?n 0)
then FALSE
else (is-even (- (abs ?n) 1))))
CLIPS> (is-even 2)
TRUE
CLIPS> (is-odd 2)
FALSE
CLIPS> (is-odd -7)
TRUE
CLIPS
```

```
CLIPS Basic Programming Guide 79
```

## Section 8: Generic Functions

With the defgeneric and defmethod constructs, new generic functions may be written directly in
CLIPS. Generic functions are similar to deffunctions because they can be used to define new
procedural code directly in CLIPS, and they can be called like any other function. However,
generic functions are much more powerful because they can do different things depending on the
types (or classes) and number of their arguments. For example, a “+” operator could be defined
which performs concatenation for strings but still performs arithmetic addition for numbers.
Generic functions are comprised of multiple components called methods, where each method
handles different cases of arguments for the generic function. A generic function which has more
than one method is said to be overloaded.

Generic functions can have system functions and user-defined external functions as implicit
methods. For example, an overloading of the “+” operator to handle strings consists of two
methods: 1) an implicit one which is the system function handling numerical addition, and 2) an
explicit (user-defined) one handling string concatenation. Deffunctions, however, may not be
methods of generic functions because they are subsumed by generic functions anyway.
Deffunctions are only provided so that basic new functions can be added directly in CLIPS without
the concerns of overloading. For example, a generic function that has only one method that restricts
only the number of arguments is equivalent to a deffunction.

In most cases, generic function methods are not called directly (the call-specific-method function
can be used to do so, however). CLIPS recognizes that a function call is generic and uses the
generic function’s arguments to find and execute the appropriate method. This process is termed
the generic dispatch.

### 8.1 Note on the Use of the Term Method.................................................................................

Most OOP systems support procedural behavior of objects either through message-passing (e.g.
Smalltalk) or by generic functions (e.g. CLOS). CLIPS supports both of these mechanisms,
although generic functions are not strictly part of COOL. A generic function may examine the
classes of its arguments but must still use messages within the bodies of its methods to manipulate
any arguments that are instances of user-defined classes. The fact that CLIPS supports both
mechanisms leads to confusion in terminology. In OOP systems that support message-passing
only, the term method is used to denote the different implementations of a message for different
classes. In systems that support generic functions only, however, the term method is used to denote
the different implementations of a generic function for different sets of argument restrictions. To
avoid this confusion, the term message-handler is used to take the place of method in the context
of messages. Thus in CLIPS, message-handlers denote the different implementations of a

```
80 Section 8: Generic Functions
```

message for different classes, and methods denote the different implementations of a generic
function for different sets of argument restrictions.

### 8.2 Performance Penalty of Generic Functions

A call to a generic function is computationally more expensive than a call to a system function,
user-defined external function, or deffunction. This is because CLIPS must first examine the
function arguments to determine which method is applicable. A performance penalty of 15%-20%
is not unexpected. In practice, generic functions should always have at least two methods.
Deffunctions or user-defined external functions should be used when overloading is not required.
A system or user-defined external function that is not overloaded will, of course, execute as quickly
as ever, since the generic dispatch is unnecessary.

### 8.3 Order Dependence of Generic Function Definitions

If a construct which uses a system or user-defined external function is loaded before a generic
function that uses that function as an implicit method, all calls to that function from that construct
will bypass the generic dispatch. For example, if a generic function which overloads the “+”
operator is defined after a rule which uses the “+” operator, that rule will always call the “+” system
function directly. However, similar rules defined after the generic function will use the generic
dispatch.

### 8.4 Defining a New Generic Function

A generic function is comprised of a header (similar to a forward declaration) and zero or more
methods. A generic function header can either be explicitly declared by the user or implicitly
declared by the definition of at least one method. A method is comprised of six elements: 1) a
name (which identifies to which generic function the method belongs), 2) an optional index, 3) an
optional comment, 4) a set of parameter restrictions, 5) an optional wildcard parameter restriction
to handle a variable number of arguments and 6) a sequence of actions, or expressions, which will
be executed in order when the method is called. The parameter restrictions are used by the generic
dispatch to determine a method’s applicability to a set of arguments when the generic function is
actually called. The defgeneric construct is used to specify the generic function header, and the
defmethod construct is used for each of the generic function’s methods.

```
CLIPS Basic Programming Guide 81
```

Syntax

```
(defgeneric <name> [<comment>])
```

```
(defmethod <name> [<index>] [<comment>]
(<parameter-restriction>* [<wildcard-parameter-restriction>])
<action>*)
```

```
<parameter-restriction> ::=
<single-field-variable> |
(<single-field-variable> <type>* [<query>])
```

```
<wildcard-parameter-restriction> ::=
<multifield-variable> |
(<multifield-variable> <type>* [<query>])
```

```
<type> ::= <class-name>
<query> ::= <global-variable> |
<function-call>
```

A generic function must be declared, either by a header or a method, prior to being called from
another generic function method, deffunction, object message-handler, rule, or the REPL. The only
exception is a self recursive generic function.

#### 8.4.1 Generic Function Headers.........................................................................................

A generic function is uniquely identified by name. In order to reference a generic function in other
constructs before any of its methods are declared, an explicit header is necessary. Otherwise, the
declaration of the first method implicitly creates a header. For example, two generic functions
whose methods mutually call the other generic function (mutually recursive generic functions)
would require explicit headers.

#### 8.4.2 Method Indices..........................................................................................................

A method is uniquely identified by name and index, or by name and parameter restrictions. Each
method for a generic function is assigned a unique integer index within the group of all methods
for that generic function. Thus, if a new method is defined which has exactly the same name and
parameter restrictions as another method, CLIPS will automatically replace the older method.
However, any difference in parameter restrictions will cause the new method to be defined in
addition to the older method. To replace an old method with one that has different parameter
restrictions, the index of the old method can be explicitly specified in the new method definition.
However, the parameter restrictions of the new method must not match that of another method
with a different index. If an index is not specified, CLIPS assigns an index that has never been
used by any method (past or current) of this generic function. The index assigned by CLIPS can
be determined with the list-defmethods command.

```
82 Section 8: Generic Functions
```

#### 8.4.3 Method Parameter Restrictions

Each parameter for a method can be defined to have arbitrarily complex restrictions or none at all.
A parameter restriction is applied to a generic function argument at run-time to determine if a
particular method will accept the argument. A parameter can have two types of restrictions: type
and query. A type restriction constrains the classes of arguments that will be accepted for a
parameter. A query restriction is a user-defined boolean test which must be satisfied for an
argument to be acceptable. The complexity of parameter restrictions directly affects the speed of
the generic dispatch.

A parameter that has no restrictions means that the method will accept any argument in that
position. However, each method of a generic function must have parameter restrictions that make
it distinguishable from all of the other methods so that the generic dispatch can tell which one to
call at run-time. If there are no applicable methods for a particular generic function call, CLIPS
will generate an error.

A type restriction allows the user to specify a list of types (or classes), one of which must match
(or be a superclass of) the class of the generic function argument. If COOL is not installed in the
current CLIPS configuration, the only types (or classes) available are: OBJECT, PRIMITIVE,
LEXEME, SYMBOL, STRING, NUMBER, INTEGER, FLOAT, MULTIFIELD,
FACT-ADDRESS and EXTERNAL-ADDRESS. With COOL, INSTANCE,
INSTANCE-ADDRESS, INSTANCE-NAME, USER, and any user-defined classes are also
available. Generic functions that use only the first group of types in their methods will work the
same whether COOL is installed or not. The classes in a type restriction must be defined already,
since they are used to predetermine the precedence between a generic function’s methods.
Redundant classes are not allowed in restriction class lists. For example, the following method
parameter’s type restriction is redundant since INTEGER is a subclass of NUMBER.

Example

```
(defmethod process ((?a INTEGER NUMBER)))
```

If the type restriction (if any) is satisfied for an argument, then a query restriction (if any) will be
applied. The query restriction must either be a global variable or a function call. CLIPS evaluates
this expression, and if it evaluates to anything but the symbol FALSE, the restriction is considered
satisfied. Since a query restriction is not always satisfied, queries should not have any side-effects,
for they will be evaluated for a method that may not end up being applicable to the generic function
call. Since parameter restrictions are examined from left to right, queries that involve multiple
parameters should be included with the rightmost parameter. This insures that all parameter type
restrictions have already been satisfied. For example, the following method delays evaluation of
the query restriction until the classes of both arguments have been verified.

```
CLIPS Basic Programming Guide 83
```

Example

```
(defmethod process ((?a INTEGER) (?b INTEGER (> ?a ?b))))
```

If the argument passes all these tests, it is deemed acceptable to a method. If all generic function
arguments are accepted by a method’s restrictions, the method itself is deemed applicable to the
set of arguments. When more than one method is applicable to a set of arguments, the generic
dispatch must determine an ordering among them and execute the first one in that ordering. Method
precedence is used for this purpose.

Example

In the following example, the first call to the generic function “+” executes the system operator
“+”, an implicit method for numerical addition. The second call executes the explicit method for
string concatenation, since there are two arguments and they are both strings. The third call
generates an error because the explicit method for string concatenation only accepts two arguments
and the implicit method for numerical addition does not accept strings at all.

```
CLIPS> (clear)
CLIPS>
(defmethod + ((?a STRING) (?b STRING))
(str-cat ?a ?b))
CLIPS> (+ 1 2)
3
CLIPS> (+ "1" "2")
"12"
CLIPS> (+ "1" "2" "3")
[GENRCEXE1] No applicable methods for '+'.
FALSE
CLIPS>
```

#### 8.4.4 Method Wildcard Parameter

A method may accept exactly or at least a specified number of arguments, depending on whether
a wildcard parameter is used or not. The regular parameters specify the minimum number of
arguments that must be passed to the method. Each of these parameters may be referenced like a
normal single-field variable within the actions of the method. If a wildcard parameter is present,
the method may be passed any number of arguments greater than or equal to the minimum. If no
wildcard parameter is present, then the method must be passed exactly the number of arguments
specified by the regular parameters. Method arguments that do not correspond to a regular
parameter can be grouped into a multifield value that can be referenced by the wildcard parameter
within the body of the method. The standard CLIPS multifield functions, such as length$ and
expand$, can be applied to the wildcard parameter.

```
84 Section 8: Generic Functions
```

If multifield values are passed as extra arguments, they will all be merged into one multifield value
referenced by the wildcard parameter. This is because CLIPS does not support nested multifield
values.

Type and query restrictions can be applied to arguments grouped in the wildcard parameter
similarly to regular parameters. Such restrictions apply to each individual field of the resulting
multifield value (not the entire multifield). However, expressions involving the wildcard parameter
variable may be used in the query. In addition, a special variable may be used in query restrictions
on the wildcard parameter to refer to the individual arguments grouped into the wildcard:
?current-argument. This variable is only in scope within the query and has no meaning in the
body of the method. For example, to create a version of the ‘+’ operator which acts differently for
sums of all even integers:

Example

```
CLIPS>
(defmethod +
(($?any INTEGER (evenp ?current-argument)))
(div (call-next-method) 2))
CLIPS> (+ 1 2)
3
CLIPS> (+ 4 6 4)
7
CLIPS>
```

It is important to emphasize that query and type restrictions on the wildcard parameter are applied
to every argument grouped in the wildcard. Thus in the following example, the > and length$
functions are actually called three times, since there are three arguments:

Example

```
CLIPS> (defmethod many (($?args (> (length$ ?args) 2))) yes)
CLIPS> (many apple pear lemon)
yes
CLIPS>
```

In addition, a query restriction will never be examined if there are no arguments in the wildcard
parameter range. For example, the previous method would be applicable to a call to the generic
function with no arguments because the query restriction is never evaluated:

Example

```
CLIPS> (many)
yes
CLIPS>
```

Typically query restrictions applied to the entire wildcard parameter are testing the cardinality (the
number of arguments passed to the method). In cases like this where the type is irrelevant to the

```
CLIPS Basic Programming Guide 85
```

test, the query restriction can be attached to a regular parameter instead to improve performance.
Thus the previous method could be improved as follows:

Example

```
CLIPS> (clear)
CLIPS> (defmethod many ((?arg (> (length$ ?args) 1)) $?args) yes)
CLIPS> (many apple pear lemon)
yes
CLIPS> (many)
[GENRCEXE1] No applicable methods for 'many'.
FALSE
CLIPS>
```

This approach should not be used if the types of the arguments grouped by the wildcard must be
verified prior to safely evaluating the query restriction.

### 8.5 Generic Dispatch

When a generic function is called, CLIPS selects the method for that generic function with highest
precedence for which parameter restrictions are satisfied by the arguments. This method is
executed, and its value is returned as the value of the generic function. This entire process is
referred to as the generic dispatch. Shown following is a flow diagram summary:

```
86 Section 8: Generic Functions
```

The solid arrows indicate automatic control transfer by the generic dispatch. The dashed arrows
indicate control transfer that can only be accomplished by the use or lack of the use of call-next-
method or override-next-method.

#### 8.5.1 Applicability of Methods Summary..........................................................................

An explicit (user-defined) method is applicable to a generic function call if the following three
conditions are met: 1) its name matches that of the generic function, 2) it accepts at least as many
arguments as were passed to the generic function, and 3) every argument of the generic function
satisfies the corresponding parameter restriction (if any) of the method.

Method restrictions are examined from left to right. As soon as one restriction is not satisfied, the
method is abandoned, and the rest of the restrictions (if any) are not examined.

```
DONE: Return control and values to caller.
```

```
ERROR:There are no applicable methods for this
generic function. Return control to caller.
```

```
START: Input is a ranked list of applicable methods.
```

```
METHOD STEP: Are there any uncalled methods?
YES: Call the next most specific method.
If the body uses call-next-method or
override-next-method, repeat this step.
Else go to DONE.
When body returns, return its values to caller.
NO: Go to ERROR.
```

```
CLIPS Basic Programming Guide 87
```

When a standard CLIPS system function is overloaded, CLIPS forms an implicit method definition
corresponding to that system function. This implicit method is derived from the argument
restriction parameters for the AddUDF call defining that function to CLIPS (see the Advanced
Programming Guide). This string can be accessed with the function get-function-restrictions
function. The specification of this implicit method can be examined with the list-defmethods or
get-method-restrictions functions. The method that CLIPS will form for a system function can
be derived by the user from the BNF given in this document. For example,

```
(+ <number> <number>+)
```

would yield the following method for the ‘+’ function:

```
(defmethod + ((?first NUMBER) (?second NUMBER) ($?rest NUMBER))
...)
```

The method definition is used to determine the applicability and precedence of the system function
to the generic function call.

The following system functions cannot be overloaded, and CLIPS will generate an error if an
attempt is made to do so.

```
active-duplicate-instance find-all-instances
active-initialize-instance find-fact
active-make-instance find-instance
active-message-duplicate-instance foreach
active-message-modify-instance if
active-modify-instance make-instance
any-instancep initialize-instance
assert loop-for-count
bind message-duplicate-instance
break message-modify-instance
call-next-handler modify
call-next-method modify-instance
call-specific-method next-handlerp
delayed-do-for-all-facts next-methodp
delayed-do-for-all-instances object-pattern-match-delay
do-for-all-facts override-next-handler
do-for-all-instances override-next-method
do-for-fact progn
do-for-instance progn$
duplicate return
duplicate-instance switch
expand$ while
```

```
88 Section 8: Generic Functions
```

```
find-all-facts
```

#### 8.5.2 Method Precedence

When two or more methods are applicable to a particular generic function call, CLIPS must pick
the one with highest precedence for execution. Method precedence is determined when a method
is defined; the list-defmethods function can be used to examine the precedence of methods for a
generic function.

The precedence between two methods is determined by comparing their parameter restrictions. In
general, the method with the most specific parameter restrictions has the highest precedence. For
example, a method that demands an integer for a particular argument will have higher precedence
than a method which only demands a number. The exact rules of precedence between two methods
are given in order below; the result of the first rule that establishes precedence is taken.

```
1) The parameter restrictions of both methods are positionally compared from left to right. In
other words, the first parameter restriction in the first method is matched against the first
parameter restriction in the second method, and so on. The comparisons between these pairs
of parameter restrictions from the two methods determine the overall precedence between the
two methods. The result of the first pair of parameter restrictions that specifies precedence is
taken. The following rules are applied in order to a parameter pair; the result of the first rule
that establishes precedence is taken.
```

```
a) A regular parameter has precedence over a wildcard parameter.
```

```
b) The most specific type restriction on a particular parameter has priority. A class is more
specific than any of its superclasses.
```

```
c) A parameter with a query restriction has priority over one that does not.
```

```
2) The method with the greater number of regular parameters has precedence.
```

```
3) A method without a wildcard parameter has precedence over one that does
```

```
4) A method defined before another one has priority.
```

If there are multiple classes on a single restriction, determining specificity is slightly more
complicated. Since all precedence determination is done when the new method is defined, and the
actual class of the generic function argument will not be known until run-time, arbitrary (but
deterministic) rules are needed for determining the precedence between two class lists. The two
class lists are examined by pairs from left to right, e.g. the pair of first classes from both lists, the
pair of second classes from both lists and so on. The first pair containing a class and its superclass
specify precedence. The class list containing the subclass has priority. If no class pairs specify

```
CLIPS Basic Programming Guide 89
```

precedence, then the shorter class list has priority. Otherwise, the class lists do not specify
precedence between the parameter restrictions.

Example 1

```
; The system operator '+' is an implicit method ; #1
; Its definition provided by the system is:
; (defmethod + ((?a NUMBER) (?b NUMBER) ($?rest NUMBER)))
```

```
(defmethod + ((?a NUMBER) (?b INTEGER))) ; #2
```

```
(defmethod + ((?a INTEGER) (?b INTEGER))) ; #3
```

```
(defmethod + ((?a INTEGER) (?b NUMBER))) ; #4
```

```
(defmethod + ((?a NUMBER) (?b NUMBER) ; #5
($?rest PRIMITIVE)))
```

```
(defmethod + ((?a NUMBER) ; #6
(?b INTEGER (> ?b 2))))
```

```
(defmethod + ((?a INTEGER (> ?a 2)) ; #7
(?b INTEGER (> ?b 3))))
```

```
(defmethod + ((?a INTEGER (> ?a 2)) ; #8
(?b NUMBER)))
```

The precedence would be: #7, #8, #3, #4, #6, #2, #1, #5. The methods can be immediately
partitioned into three groups of decreasing precedence according to their restrictions on the first
parameter: A) methods which have a query restriction and a type restriction of INTEGER (#7, #8),
B) methods which have a type restriction of INTEGER (#3, #4), and C) methods which have a
type restriction of NUMBER (#1, #2, #5, #6). Group A has precedence over group B because
parameters with query restrictions have priority over those that do not. Group B has precedence
over group C because INTEGER is a subclass of NUMBER. Thus, the ordering so far is: (#7, #8),
(#3, #4), (#1, #2, #5, #6). Ordering between the methods in a particular set of parentheses is not
yet established.

The next step in determining precedence between these methods considers their restrictions on the
second parameter. #7 has priority over #8 because INTEGER is a subclass of NUMBER. #3 has
priority over #4 because INTEGER is a subclass of NUMBER. #6 and #2 have priority over #1
and #5 because INTEGER is a subclass of NUMBER. #6 has priority over #2 because it has a
query restriction and #2 does not. Thus the ordering is now: #7, #8, #3, #4, #6, #2, (#1, #5).

The restriction on the wildcard argument yields that #1 (the system function implicit method) has
priority over #5 since NUMBER is a subclass of PRIMITIVE. This gives the final ordering: #7,
#8, #3, #4, #6, #2, #1, #5.

```
90 Section 8: Generic Functions
```

Example 2

```
(defmethod combine ((?a NUMBER STRING))) ; #1
```

```
(defmethod combine ((?a INTEGER LEXEME))) ; #2
```

The precedence would be #2, #1. Although STRING is a subclass of LEXEME, the ordering is
still #2, #1 because INTEGER is a subclass of NUMBER, and NUMBER/INTEGER is the
leftmost pair in the class lists.

Example 3

```
(defmethod combine ((?a MULTIFIELD STRING))) ; #1
```

```
(defmethod combine ((?a LEXEME))) ; #2
```

The precedence would be #2, #1 because the classes of the first pair in the type restriction
(MULTIFIELD/LEXEME) are unrelated and #2 has fewer classes in its class list.

Example 4

```
(defmethod combine ((?a INTEGER LEXEME))) ; #1
```

```
(defmethod combine ((?a STRING NUMBER))) ; #2
```

Both pairs of classes (INTEGER/STRING and LEXEME/NUMBER) are unrelated, and the class
lists are of equal length. Thus, the precedence is taken from the order of definition: #1, #2.

#### 8.5.3 Shadowed Methods

If one method must be called by another method in order to be executed, the first function or
method is said to be shadowed by the second method. Normally, only one method or system
function will be applicable to a particular generic function call. If there is more than one applicable
method, the generic dispatch will only execute the one with highest precedence. Letting the generic
dispatch automatically handle the methods in this manner is called the declarative technique, for
the declarations of the method restrictions dictate which method gets executed in specific
circumstances. However, the call-next-method and override-next-method functions may also be
used which allow a method to execute the method that it is shadowing. This is called the
imperative technique, since the method execution itself plays a role in the generic dispatch. This
is not recommended unless it is absolutely necessary. In most circumstances, only one piece of
code should need to be executed for a particular set of arguments. Another imperative technique
is to use the call-specific-method function to override method precedence.

```
CLIPS Basic Programming Guide 91
```

#### 8.5.4 Method Execution Errors

If an error occurs while any method for a generic function call is executing, any actions in the
current method not yet executed will be aborted, any methods not yet called will be aborted, and
the generic function will return the symbol FALSE. The lack of any applicable methods for a set
of generic function arguments is considered a method execution error.

#### 8.5.5 Generic Function Return Value

The return value of a generic function is the return value of the applicable method with the highest
precedence. Each applicable method that is executed can choose to ignore or capture the return
value of any method that it is shadowing.

The return value of a particular method is the last action evaluated by that method.

```
92 Section 9: CLIPS Object Oriented Language
```

## Section 9: CLIPS Object Oriented Language

This section provides the comprehensive details of the CLIPS Object-Oriented Language (COOL).

### 9.1 Background

COOL is a hybrid of features from many different OOP systems as well as new ideas. For example,
object encapsulation concepts are similar to those in Smalltalk, and the Common Lisp Object
System (CLOS) provides the basis for multiple inheritance rules. A mixture of ideas from
Smalltalk, CLOS and other systems form the foundation of messages. Section 8.1 explains an
important contrast between the terms method and message-handler in CLIPS.

### 9.2 Predefined System Classes

COOL provides sixteen system classes: OBJECT, USER, PRIMITIVE, NUMBER, INTEGER,
FLOAT, INSTANCE, INSTANCE-NAME, INSTANCE-ADDRESS, ADDRESS,
FACT-ADDRESS, EXTERNAL-ADDRESS, MULTIFIELD, LEXEME, SYMBOL and
STRING. The user may not delete or modify any of these classes. The diagram illustrates the
inheritance relationships between these classes.

```
CLIPS Basic Programming Guide 93
```

All of these system classes are abstract classes, which means that their only use is for inheritance
(direct instances of this class are illegal). None of these classes have slots, and, except for the class
USER, none of them have message-handlers. However, the user may explicitly attach
message-handlers to all of the system classes except for INSTANCE, INSTANCE-ADDRESS and
INSTANCE-NAME. The OBJECT class is a superclass of all other classes, including user-defined
classes. All user-defined classes should (but are not required to) inherit directly or indirectly from
the class USER, since this class has all of the standard system message-handlers, such as
initialization and deletion, attached to it. Section 9.4 describes these system message-handlers.

The PRIMITIVE system class and all of its subclasses are provided mostly for use in generic
function method restrictions, but message-handlers and new subclasses may be attached if desired.
However, the three primitive system classes INSTANCE, INSTANCE-ADDRESS and
INSTANCE-NAME are provided strictly for use in methods (particularly in forming implicit
methods for overloaded system functions) and as such cannot have subclasses or message-handlers
attached to them.

```
OBJECT
```

```
PRIMITIVE USER
```

```
NUMBER
```

```
FLOAT
```

```
INSTANCE-NAME
```

```
INSTANCE
```

```
INTEGER
```

```
INSTANCE-ADDRESS FACT-ADDRESS EXTERNAL-ADDRESS
```

```
ADDRESS
```

```
MULTIFIELD LEXEME
```

```
SYMBOL STRING
```

```
94 Section 9: CLIPS Object Oriented Language
```

### 9.3 Defclass Construct

A defclass is a construct for specifying the properties (slots) and behavior (message-handlers) of
a class of objects. A defclass consists of five elements: 1) a name, 2) a list of superclasses from
which the new class inherits slots and message-handlers, 3) a specifier saying whether or not the
creation of direct instances of the new class is allowed, 4) a specifier saying whether or not
instances of this class can match object patterns on the LHS of rules and 5) a list of slots specific
to the new class. All user-defined classes must inherit from at least one class, and to this end COOL
provides predefined system classes for use as a base in the derivation of new classes.

Any slots explicitly given in the defclass override those gotten from inheritance. COOL applies
rules to the list of superclasses to generate a class precedence list for the new class. Facets further
describe slots. Some examples of facets include: default value, cardinality, and types of access
allowed.

Syntax

Defaults are in bold italics.

```
(defclass <name> [<comment>]
(is-a <superclass-name>+)
[<role>]
[<pattern-match-role>]
<slot>*
<handler-documentation>*)
```

```
<role> ::= (role concrete | abstract)
```

```
<pattern-match-role>
::= (pattern-match reactive | non-reactive)
```

```
<slot> ::= (slot <name> <facet>*) |
(single-slot <name> <facet>*) |
(multislot <name> <facet>*)
```

```
<facet> ::= <default-facet> | <storage-facet> |
<access-facet> | <propagation-facet> |
<source-facet> | <pattern-match-facet> |
<visibility-facet> | <create-accessor-facet>
<override-message-facet> | <constraint-attributes>
```

```
<default-facet> ::=
(default ?DERIVE | ?NONE | <expression>*) |
(default-dynamic <expression>*)
```

```
<storage-facet> ::= (storage local | shared)
```

```
<access-facet>
::= (access read-write | read-only | initialize-only)
```

```
CLIPS Basic Programming Guide 95
```

```
<propagation-facet> ::= (propagation inherit | no-inherit)
```

```
<source-facet> ::= (source exclusive | composite)
```

```
<pattern-match-facet>
::= (pattern-match reactive | non-reactive)
```

```
<visibility-facet> ::= (visibility private | public)
```

```
<create-accessor-facet>
::= (create-accessor ?NONE | read | write | read-write )
```

```
<override-message-facet>
::= (override-message ?DEFAULT | <message-name>)
```

```
<handler-documentation>
::= (message-handler <name> [<handler-type>])
```

```
<handler-type> ::= primary | around | before | after
```

Redefining an existing class deletes the current subclasses and all associated message-handlers.
An error will occur if instances of the class or any of its subclasses exist.

#### 9.3.1 Multiple Inheritance

If one class inherits from another class, the first class is a subclass of the second class, and the
second class is a superclass of the first class. Every user-defined class must have at least one direct
superclass, i.e. at least one class must appear in the is-a portion of the defclass. Multiple inheritance
occurs when a class has more than one direct superclass. COOL examines the direct superclass list
for a new class to establish a linear ordering called the class precedence list. The new class inherits
slots and message-handlers from each of the classes in the class precedence list. The word
precedence implies that slots and message-handlers of a class in the list override conflicting
definitions of another class found later in the list. A class that comes before another class in the
list is said to be more specific. All class precedence lists will terminate in the system class
OBJECT, and most (if not all) class precedence lists for user-defined classes will terminate in the
system classes USER and OBJECT. The class precedence list can be listed using the
describe-class function.

9.3.1.1 Multiple Inheritance Rules

COOL uses the inheritance hierarchy of the direct superclasses to determine the class precedence
list for a new class. COOL recursively applies the following two rules to the direct superclasses:

```
1) A class has higher precedence than any of its superclasses.
```

```
2) A class specifies the precedence between its direct superclasses.
```

```
96 Section 9: CLIPS Object Oriented Language
```

If more than one class precedence list would satisfy these rules, COOL chooses the one most
similar to a strict preorder depth-first traversal. This heuristic attempts to preserve “family trees”
to the greatest extent possible. For example, if a child inherited genetic traits from a mother and
father, and the mother and father each inherited traits from their parents, the child’s class
precedence list would be: child mother maternal-grandmother maternal-grandfather father
paternal-grandmother paternal-grandfather. There are other orderings which would satisfy the
rules (such as child mother father paternal-grandfather maternal-grandmother
paternal-grandmother maternal-grandfather), but COOL chooses the one which keeps the family
trees together as much as possible.

Example 1

```
(defclass A (is-a USER))
```

Class A directly inherits information from the class USER. The class precedence list for A is: A
USER OBJECT.

Example 2

```
(defclass B (is-a USER))
```

Class B directly inherits information from the class USER. The class precedence list for B is: B
USER OBJECT.

Example 3

```
(defclass C (is-a A B))
```

Class C directly inherits information from the classes A and B. The class precedence list for C is:
C A B USER OBJECT.

Example 4

```
(defclass D (is-a B A))
```

Class D directly inherits information from the classes B and A. The class precedence list for D is:
D B A USER OBJECT.

Example 5

```
(defclass E (is-a A C))
```

By rule #2, A must precede C. However, C is a subclass of A and cannot succeed A in a precedence
list without violating rule #1. Thus, this is an error.

Example 6

```
(defclass E (is-a C A))
```

```
CLIPS Basic Programming Guide 97
```

Specifying that E inherits from A is extraneous, since C inherits from A. However, this definition
does not violate any rules and is acceptable. The class precedence list for E is: E C A B USER
OBJECT.

Example 7

```
(defclass F (is-a C B))
```

Specifying that F inherits from B is extraneous, since C inherits from B. The class precedence list
for F is: F C A B USER OBJECT. The superclass list says B must follow C in F’s class precedence
list but not that B must immediately follow C.

Example 8

```
(defclass G (is-a C D))
```

This is an error, for it violates rule #2. The class precedence of C says that A should precede B,
but the class precedence list of D says the opposite.

Example 9

```
(defclass H (is-a A))
(defclass I (is-a B))
(defclass J (is-a H I A B))
```

The respective class precedence lists of H and I are: H A USER OBJECT and I B USER OBJECT.
If J did not have A and B as direct superclasses, J could have one of three possible class precedence
lists: J H A I B USER OBJECT, J H I A B USER OBJECT, or J H I B A USER OBJECT. COOL
would normally pick the first list since it preserves the family trees (H A and I B) to the greatest
extent possible. However, since J inherits directly from A and B, rule #2 dictates that the class
precedence list must be J H I A B USER OBJECT.

❖ Usage Note

For most practical applications of multiple inheritance, the order in which the superclasses are
specified should not matter. If you create a class using multiple inheritance and the order of the
classes specified in the is-a attribute effects the behavior of the class, you should consider whether
your program design is needlessly complex.

```
98 Section 9: CLIPS Object Oriented Language
```

9.3.2 Class Specifiers

9.3.2.1 Abstract and Concrete Classes

An abstract class is intended for inheritance only, and no direct instances of this class can be
created. A concrete class can have direct instances. Using the abstract role specifier in a defclass
will cause COOL to generate an error if make-instance is ever called for this class. If the abstract
or concrete descriptor for a class is not specified, it is determined by inheritance. For the purpose
of role inheritance, system defined classes behave as concrete classes. Thus a class which inherits
from USER will be concrete if no role is specified.

9.3.2.2 Reactive and Non-Reactive Classes

Objects of a reactive class can match object patterns in a rule. Objects of a non-reactive class
cannot match object patterns in a rule and are not considered when the list of applicable classes
are determined for an object pattern. An abstract class cannot be reactive. If the reactive or
non-reactive descriptor for a class is not specified, it is determined by inheritance. For the purpose
of pattern-match inheritance, system defined classes behave as reactive classes unless the
inheriting class is abstract.

#### 9.3.3 Slots...........................................................................................................................

Slots are placeholders for values associated with instances of a user-defined class. Each instance
has a copy of the set of slots specified by the immediate class as well as any obtained from
inheritance. The name of a slot may be any symbol with the exception of the keywords is-a and
name which are reserved for use in object patterns.

To determine the set of slots for an instance, the class precedence list for the instance’s class is
examined in order from most specific to most general (left to right). A class is more specific than
its superclasses. Slots specified in any of the classes in the class precedence list are given to the
instance, with the exception of no-inherit slots. If a slot is inherited from more than one class, the
definition given by the more specific class takes precedence, with the exception of composite slots.

Example

```
(defclass VEHICLE (is-a USER)
(slot wheels)
(slot engine))
```

```
(defclass CAR (is-a VEHICLE)
(slot make)
(slot model))
```

```
CLIPS Basic Programming Guide 99
```

The class precedence list of VEHICLE is: VEHICLE USER OBJECT. Instances of VEHICLE
will have two slots: wheels and engine. The class precedence list of CAR is: CAR VEHICLE
USER OBJECT. Instances of CAR will have four slots: make, model, wheels, and engine.

Just as slots make up classes, facets make up slots. Facets describe various features of a slot that
hold true for all objects which have the slot: default value, storage, access, inheritance propagation,
source of other facets, pattern-matching reactivity, visibility to subclass message-handlers, the
automatic creation of message-handlers to access the slot, the name of the message to send to set
the slot, and constraint information. Each object can still have its own value for a slot, with the
exception of shared slots.

9.3.3.1 Slot Field Type

A slot can hold either a single-field or multifield value. The keyword multislot specifies that a slot
can hold a multifield value comprised of zero or more fields, and the keyword slot specifies that
the slot can hold one value. Multifield slot values are stored as multifield values and can be
manipulated with the standard multifield functions, such as nth$ and length$, once they are
retrieved via messages. COOL also provides functions for setting multifield slots, such as
slot-insert$. Single-field slots are stored as a CLIPS primitive type, such as integer or string.

Example

```
CLIPS> (clear)
CLIPS>
(defclass GROCERY-LIST (is-a USER)
(multislot items
(default milk eggs bread)))
CLIPS> (make-instance list of GROCERY-LIST)
[list]
CLIPS> (send [list] get-items)
(milk eggs bread)
CLIPS>
```

9.3.3.2 Default Value Facet

The default and default-dynamic facets can be used to specify an initial value given to a slot
when an instance of the class is created or initialized. By default, a slot will have a default value
that is derived from the slot’s constraint facets. Default values are directly assigned to slots without
the use of messages, unlike slot overrides in a make-instance call.

The default facet is a static default: the specified expression is evaluated once when the class is
defined, and the result is stored with the class. This result is assigned to the appropriate slot when
a new instance is created. If the keyword ?DERIVE is used for the default value, then a default
value is derived from the constraints for the slot. By default, the default attribute for a slot is

```
100 Section 9: CLIPS Object Oriented Language
```

(default ?DERIVE). If the keyword ?NONE is used for the default value, then the slot is not
assigned a default value. Using this keyword causes make-instance to require a slot-override for
that slot when an instance is created.

The default-dynamic facet is a dynamic default: the specified expression is evaluated every time
an instance is created, and the result is assigned to the appropriate slot.

Example

```
CLIPS> (clear)
CLIPS>
(deffunction timestring ()
(bind ?date (local-time))
(format nil "%d-%02d-%02d %02d:%02d:%02d"
(nth$ 1 ?date)
(nth$ 2 ?date)
(nth$ 3 ?date)
(nth$ 4 ?date)
(nth$ 5 ?date)
(nth$ 6 ?date)))
CLIPS>
(deffunction wait-a-second ()
(bind ?second (nth$ 6 (local-time)))
(while (= ?second (nth$ 6 (local-time))))
(return done))
CLIPS>
(defclass VEHICLE
(is-a USER)
(slot created (default-dynamic (timestring)))
(slot wheels (default 4))
(slot engine (allowed-values gas diesel)))
CLIPS>
(defclass CAR
(is-a VEHICLE)
(slot make (type STRING))
(slot model (type STRING)))
CLIPS> (make-instance v1 of VEHICLE)
[v1]
CLIPS> (send [v1] print)
[v1] of VEHICLE
(created "2018- 05 - 23 23:50:37")
(wheels 4)
(engine gas)
CLIPS> (wait-a-second)
done
CLIPS> (make-instance c1 of CAR (make "Astro") (model "Comet") (wheels 4))
[c1]
CLIPS> (send [c1] print)
[c1] of CAR
(created "2018- 05 - 23 23:50:38")
(wheels 4)
(engine gas)
(make "Astro")
```

```
CLIPS Basic Programming Guide 101
```

```
(model "Comet")
CLIPS> (wait-a-second)
done
CLIPS> (make-instance c2 of CAR (wheels 6) (engine diesel))
[c2]
CLIPS> (send [c2] print)
[c2] of CAR
(created "2018- 05 - 23 23:50:39")
(wheels 6)
(engine diesel)
(make "")
(model "")
CLIPS>
```

9.3.3.3 Storage Facet

The actual value of an instance’s copy of a slot can either be stored with the instance or with the
class. The local facet specifies that the value be stored with the instance, and this is the default.
The shared facet specifies that the value be stored with the class. If the slot value is locally stored,
then each instance can have a separate value for the slot. However, if the slot value is stored with
the class, all instances will have the same value for the slot. Anytime the value is changed for a
shared slot, it will be changed for all instances with that slot.

A shared slot will always pick up a dynamic default value from a defclass when an instance is
created or initialized, but the shared slot will ignore a static default value unless it does not
currently have a value. Any changes to a shared slot will cause pattern-matching for rules to be
updated for all reactive instances containing that slot.

Example 1

```
CLIPS> (clear)
CLIPS>
(defclass VEHICLE
(is-a USER)
(slot vehicle-count
(storage shared)
(default 0)))
CLIPS>
(defmessage-handler VEHICLE init after ()
(bind ?self:vehicle-count (+ ?self:vehicle-count 1)))
CLIPS>
(defmessage-handler VEHICLE delete before ()
(bind ?self:vehicle-count (- ?self:vehicle-count 1)))
CLIPS> (make-instance v1 of VEHICLE)
[v1]
CLIPS> (send [v1] get-vehicle-count)
1
CLIPS> (make-instance v2 of VEHICLE)
[v2]
CLIPS> (send [v1] get-vehicle-count)
```

```
102 Section 9: CLIPS Object Oriented Language
```

```
2
CLIPS> (send [v2] get-vehicle-count)
2
CLIPS> (send [v1] delete)
TRUE
CLIPS> (send [v2] get-vehicle-count)
1
CLIPS>
```

Example 2

```
CLIPS> (clear)
CLIPS>
(deffunction timestring ()
(bind ?date (local-time))
(format nil "%d-%02d-%02d %02d:%02d:%02d"
(nth$ 1 ?date)
(nth$ 2 ?date)
(nth$ 3 ?date)
(nth$ 4 ?date)
(nth$ 5 ?date)
(nth$ 6 ?date)))
CLIPS>
(deffunction wait-a-second ()
(bind ?second (nth$ 6 (local-time)))
(while (= ?second (nth$ 6 (local-time))))
(return done))
CLIPS>
(defclass VEHICLE
(is-a USER)
(slot last-creation
(storage shared)
(default-dynamic (timestring))))
CLIPS> (make-instance v1 of VEHICLE)
[v1]
CLIPS> (send [v1] get-last-creation)
"2018- 05 - 23 19:24:43"
CLIPS> (wait-a-second)
done
CLIPS> (make-instance v2 of VEHICLE)
[v2]
CLIPS> (send [v1] get-last-creation)
"2018- 05 - 23 19:24:44"
CLIPS> (send [v2] get-last-creation)
"2018- 05 - 23 19:24:44"
CLIPS>
```

9.3.3.4 Access Facet

There are three types of access facets which can be specified for a slot: read-write, read-only,
and initialize-only. The read-write facet is the default and specifies that a slot can be both written
and read. The read-only facet specifies the slot can only be read; the only way to set this slot is

```
CLIPS Basic Programming Guide 103
```

with default facets in the class definition. The initialize-only facet is like read-only except that
the slot can also be set by slot overrides in a make-instance call and init message-handlers. These
privileges apply to indirect access via messages as well as direct access within message-handler
bodies. Note: a read-only slot that has a static default value will implicitly have the shared storage
facet.

Example

```
CLIPS> (clear)
CLIPS>
(deffunction datestring ()
(bind ?date (local-time))
(format nil "%d-%02d-%02d"
(nth$ 1 ?date)
(nth$ 2 ?date)
(nth$ 3 ?date)))
CLIPS>
(defclass VEHICLE
(is-a USER)
(slot created
(access read-only)
(default-dynamic (datestring)))
(slot manufactured
(access initialize-only))
(slot modified
(access read-write)))
CLIPS> (make-instance v1 of VEHICLE (created "2018- 05 - 17"))
[MSGFUN1] No applicable primary message-handlers found for 'put-created'.
FALSE
CLIPS> (make-instance v1 of VEHICLE (manufactured "2018- 05 - 17") (modified "2018-
05 - 17"))
[v1]
CLIPS> (send [v1] put-manufactured "2019- 12 - 24")
[MSGFUN3] Write access denied for slot 'manufactured' in instance [v1] of class
'VEHICLE'.
[PRCCODE4] Execution halted during the actions of message-handler 'put-
manufactured' primary in class 'VEHICLE'
FALSE
CLIPS> (send [v1] put-created "2019- 12 - 24")
[MSGFUN1] No applicable primary message-handlers found for 'put-created'.
FALSE
CLIPS> (send [v1] put-modified "2019- 12 - 24")
"2019- 12 - 24"
CLIPS> (send [v1] print)
[v1] of VEHICLE
(created "2018- 05 - 24")
(manufactured "2018- 05 - 17")
(modified "2019- 12 - 24")
CLIPS>
```

```
104 Section 9: CLIPS Object Oriented Language
```

9.3.3.5 Inheritance Propagation Facet

An inherit facet specifies that a slot in a class can be given to instances of other classes that inherit
from the first class. This is the default. The no-inherit specifies that only direct instances of this
class will get the slot.

Example

```
CLIPS> (clear)
CLIPS>
(defclass PERSON (is-a USER)
(slot full-name)
(slot age)
(slot SSN (propagation no-inherit)))
CLIPS>
(defclass SECURE-PERSON (is-a PERSON))
CLIPS>
(make-instance p of PERSON
(full-name "Sam Jones")
(age 35)
(SSN 738- 93 - 2736))
[p]
CLIPS>
(make-instance sp of SECURE-PERSON
(full-name "Sally Smith")
(age 28))
[sp]
CLIPS> (send [p] print)
[p] of PERSON
(full-name "Sam Jones")
(age 35)
(SSN 738- 93 - 2736)
CLIPS> (send [sp] print)
[sp] of SECURE-PERSON
(full-name "Sally Smith")
(age 28)
CLIPS>
```

9.3.3.6 Source Facet

When obtaining slots from the class precedence list during instance creation, the default behavior
is to take the facets from the most specific class that defines the slot and assign default values to
any unspecified facets. This is the behavior specified by the exclusive facet. The composite facet
causes facets which are not explicitly specified by the most specific class to be taken from the next
most specific class. Thus, in an overlay fashion, the facets of an instance’s slot can be specified by
more than one class. Note that even though facets may be taken from superclasses, the slot is still
considered to reside in the new class for purposes of visibility. One use of this feature is to pick
up a slot definition and change only its default value for a new derived class.

```
CLIPS Basic Programming Guide 105
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass PERSON (is-a USER)
(slot full-name (default ""))
(slot age (default 0)))
CLIPS>
(defclass LOCKED-PERSON (is-a PERSON)
(slot full-name
(source composite)
(access initialize-only)))
CLIPS> (make-instance p of PERSON)
[p]
CLIPS> (send [p] print)
[p] of PERSON
(full-name "")
(age 0)
CLIPS> (send [p] put-full-name "Sam Jones")
"Sam Jones"
CLIPS> (make-instance lp of LOCKED-PERSON)
[lp]
CLIPS> (send [lp] print)
[lp] of LOCKED-PERSON
(age 0)
(full-name "")
CLIPS> (send [lp] put-full-name "Sally Smith")
[MSGFUN3] Write access denied for slot 'full-name' in instance [lp] of class
'LOCKED-PERSON'.
[PRCCODE4] Execution halted during the actions of message-handler 'put-full-name'
primary in class 'LOCKED-PERSON'
FALSE
CLIPS>
```

9.3.3.7 Pattern-Match Reactivity Facet

Normally, any change to a slot of an instance will be considered as a change to the instance for
purposes of pattern-matching. However, it is possible to indicate that changes to a slot of an
instance should not cause pattern-matching. The reactive facet specifies that changes to a slot
trigger pattern-matching, and this is the default. The non-reactive facet specifies that changes to
a slot do not affect pattern-matching.

Example

```
CLIPS> (clear)
CLIPS>
(defclass PERSON (is-a USER)
(slot full-name)
(slot age))
CLIPS>
(defclass WINE-BOTTLE (is-a USER)
```

```
106 Section 9: CLIPS Object Oriented Language
```

```
(slot wine-name)
(slot age (pattern-match non-reactive)))
CLIPS>
(defrule created
?ins <- (object (is-a PERSON | WINE-BOTTLE))
=>
(println "Created " (instance-name ?ins)))
CLIPS>
(defrule birthday
?ins <- (object (is-a PERSON | WINE-BOTTLE)
(age ?))
=>
(println "Happy Birthday " (instance-name ?ins)))
CLIPS> (make-instance p1 of PERSON (full-name "Jack Smith") (age 34))
[p1]
CLIPS> (make-instance w1 of WINE-BOTTLE (wine-name "Pinot Noir") (age 2))
[w1]
CLIPS> (run)
Created [w1]
Created [p1]
Happy Birthday [p1]
CLIPS> (send [p1] put-age 35)
35
CLIPS> (send [w1] put-age 3)
3
CLIPS> (run)
Happy Birthday [p1]
CLIPS>
```

9.3.3.8 Visibility Facet

Normally, only message-handlers attached to the class in which a slot is defined may directly
access the slot. However, it is possible to allow message-handlers attached to superclasses or
subclasses which inherit the slot to directly access the slot as well. Declaring the visibility facet to
be private specifies that only the message-handlers of the defining class may directly access the
slot, and this is the default. Declaring the visibility facet to be public specifies that the
message-handlers and subclasses that inherit the slot and superclasses may also directly access the
slot.

Example

```
CLIPS> (clear)
CLIPS>
(defclass CUSTOMER (is-a USER)
(slot full-name)
(slot cid (visibility public)))
CLIPS>
(defclass VALUED-CUSTOMER (is-a CUSTOMER)
(slot reward-points))
CLIPS>
(defmessage-handler VALUED-CUSTOMER id-string ()
```

```
CLIPS Basic Programming Guide 107
```

```
(str-cat ?self:full-name " " ?self:cid " " ?self:reward-points))
```

```
[MSGFUN6] Private slot 'full-name' of class 'CUSTOMER' cannot be accessed
directly by handlers attached to class 'VALUED-CUSTOMER'
```

```
ERROR:
(defmessage-handler MAIN::VALUED-CUSTOMER id-string
()
(str-cat ?self:full-name " " ?self:cid " " ?self:reward-points)
)
CLIPS>
(defmessage-handler VALUED-CUSTOMER id-string ()
(str-cat ?self:cid " " ?self:reward-points))
CLIPS>
```

9.3.3.9 Create-Accessor Facet

The create-accessor facet instructs CLIPS to automatically create explicit message-handlers for
reading and/or writing a slot. By default, implicit slot-accessor message-handlers are created for
every slot. While these message-handlers are real message-handlers and can be manipulated as
such, they have no pretty-print form and cannot be directly modified by the user.

If the value ?NONE is specified for the facet, no message-handlers are created.

If the value read is specified for the facet, CLIPS creates the following message-handler:

```
(defmessage-handler <class> get-<slot-name> primary ()
?self:<slot-name>)
```

If the value write is specified for the facet, CLIPS creates the following message-handler for
single-field slots:

```
(defmessage-handler <class> put-<slot-name> primary (?value)
(bind ?self:<slot-name> ?value)
```

or the following message-handler for multifield slots:

```
(defmessage-handler <class> put-<slot-name> primary ($?value)
(bind ?self:<slot-name> ?value)
```

If the value read-write is specified for the facet, both the get- and put- message-handlers are
created.

If accessors are required that do not use static slot references, then user must define them explicitly
with the defmessage-handler construct.

```
108 Section 9: CLIPS Object Oriented Language
```

The access facet affects the default value for the create-accessor facet. If the access facet is read-
write, then the default value for the create-accessor facet is read-write. If the access facet is
read-only, then the default value is read. If the access facet is initialize-only, then the default is
?NONE.

Example

```
CLIPS> (clear)
CLIPS>
(defclass PERSON (is-a USER)
(slot full-name)
(slot age)
(slot SSN))
CLIPS> (clear)
CLIPS>
(defclass PERSON (is-a USER)
(slot full-name (default "") (create-accessor read))
(slot age (default 0) (create-accessor write))
(slot SSN (default XXX-XX-XXXX) (create-accessor read-write)))
CLIPS> (make-instance p1 of PERSON)
[p1]
CLIPS> (send [p1] get-full-name)
""
CLIPS> (send [p1] get-age)
[MSGFUN1] No applicable primary message-handlers found for 'get-age'.
FALSE
CLIPS> (send [p1] get-SSN)
XXX-XX-XXXX
CLIPS> (send [p1] put-full-name "Jack Smith")
[MSGFUN1] No applicable primary message-handlers found for 'put-full-name'.
FALSE
CLIPS> (send [p1] put-age 37)
37
CLIPS> (send [p1] put-SSN 736- 98 - 2345)
736 - 98 - 2345
CLIPS>
```

9.3.3.10 Override-Message Facet

There are several COOL support functions that set slots via use of message-passing, e.g.,
make-instance, initialize-instance, message-modify-instance, and message-duplicate-
instance. By default, all these functions attempt to set a slot with the message called
put-<slot-name>. However, if the user has elected not to use standard slot-accessors and wishes
these functions to be able to perform slot-overrides, then the override-message facet can be used
to indicate what message to send instead.

Example

```
CLIPS> (clear)
CLIPS>
```

```
CLIPS Basic Programming Guide 109
```

```
(defclass PERSON (is-a USER)
(slot full-name)
(slot age (default 0) (override-message my-put-age)))
CLIPS>
(defmessage-handler PERSON my-put-age (?value)
(if (and (integerp ?value) (>= ?value 0))
then
(bind ?self:age ?value)))
CLIPS> (watch messages)
CLIPS> (make-instance p1 of PERSON (full-name "Jack Smith") (age 37))
MSG >> create ED:1 (<Instance-p1>)
MSG << create ED:1 (<Instance-p1>)
MSG >> put-full-name ED:1 (<Instance-p1> "Jack Smith")
MSG << put-full-name ED:1 (<Instance-p1> "Jack Smith")
MSG >> my-put-age ED:1 (<Instance-p1> 37)
MSG << my-put-age ED:1 (<Instance-p1> 37)
MSG >> init ED:1 (<Instance-p1>)
MSG << init ED:1 (<Instance-p1>)
[p1]
CLIPS> (unwatch messages)
CLIPS>
```

9.3.3.11 Constraint Facets

The syntax and functionality of single and multifield constraint facets (attributes) are described in
detail in Section 11. Static and dynamic constraint checking for classes and their instances is
supported. Static checking is performed when constructs or commands that specify slot
information are being parsed. Object patterns used on the LHS of a rule are also checked to
determine if constraint conflicts exist among variables used in more that one slot. Errors for
inappropriate values are immediately signaled. Static checking is always enabled. Dynamic
checking is also supported. If dynamic checking is enabled, then new instances have their values
checked whenever they are set (e.g. initialization, slot-overrides, and put- access). Dynamic
checking is disabled by default. This behavior can be changed using the
set-dynamic-constraint-checking function. If an violation occurs when dynamic checking is
being performed, then execution will be halted.

Regardless of whether dynamic checking is enabled, multifield values can never be stored in
single-field slots. Single-field values are converted to a multifield value of length one when storing
in a multifield slot. In addition, the evaluation of a function that has no return value is always
illegal as a slot value.

Example

```
CLIPS> (clear)
CLIPS>
(defclass LINE (is-a USER)
(multislot coordinates
(type INTEGER)
(cardinality 2 2)))
```

```
110 Section 9: CLIPS Object Oriented Language
```

```
CLIPS> (make-instance l1 of LINE (coordinates five seven))
[l1]
CLIPS> (set-dynamic-constraint-checking TRUE)
FALSE
CLIPS> (make-instance l1 of LINE (coordinates two three))
[CSTRNCHK1] The value (two three) for slot 'coordinates' of instance [l1] found
in 'put-coordinates' primary in class 'LINE' does not match the allowed types.
[PRCCODE4] Execution halted during the actions of message-handler 'put-
coordinates' primary in class 'LINE'
FALSE
CLIPS> (make-instance l1 of LINE (coordinates 2))
[CSTRNCHK1] The value (2) for slot 'coordinates' of instance [l1] found in 'put-
coordinates' primary in class 'LINE' does not satisfy the cardinality
restrictions.
[PRCCODE4] Execution halted during the actions of message-handler 'put-
coordinates' primary in class 'LINE'
FALSE
CLIPS> (set-dynamic-constraint-checking FALSE)
TRUE
CLIPS>
```

#### 9.3.4 Message-handler Documentation............................................................................

COOL allows the user to forward declare the message-handlers for a class within the defclass
statement. These declarations are for documentation only and are ignored by CLIPS. The
defmessage-handler construct must be used to actually add message-handlers to a class.
Message-handlers can later be added which are not documented in the defclass.

Example

```
CLIPS> (clear)
CLIPS>
(defclass RECTANGLE
(is-a USER)
(slot length (default 1))
(slot width (default 1))
(message-handler get-area))
CLIPS>
(defmessage-handler RECTANGLE get-area ()
(* ?self:width ?self:length))
CLIPS>
(defmessage-handler RECTANGLE print-area ()
(println (send ?self get-area)))
CLIPS>
```

### 9.4 Defmessage-handler Construct

Objects are manipulated by sending them messages via the send function. The result of a message
is a useful return-value or side-effect. A defmessage-handler is a construct for specifying the
behavior of a class of objects in response to a particular message. The implementation of a message

```
CLIPS Basic Programming Guide 111
```

is made up of pieces of procedural code called message-handlers (or handlers for short). Each class
in the class precedence list of an object’s class can have handlers for a message. In this way, the
object’s class and all its superclasses share the labor of handling the message. Each class’s handlers
handle the part of the message that is appropriate to that class. Within a class, the handlers for a
particular message can be further subdivided into four types or categories: primary, before, after
and around. The intended purposes of each type are summarized in the chart below:

```
Type Role for the Class
primary Performs the majority of the work for the message
before Does auxiliary work for a message before the primary handler executes
after Does auxiliary work for a message after the primary handler executes
around Sets up an environment for the execution of the rest of the handlers
```

Before and after handlers are for side-effects only; their return values are always ignored. Before
handlers execute before the primary ones, and after message-handlers execute after the primary
ones. The return value of a message is generally given by the primary message-handlers, but
around handlers can also return a value. Around message-handlers allow the user to wrap code
around the rest of the handlers. They begin execution before the other handlers and pick up again
after all the other message-handlers have finished.

A primary handler provides the part of the message implementation which is most specific to an
object, and thus the primary handler attached to the class closest to the immediate class of the
object overrides other primary handlers. Before and after handlers provide the ability to pick up
behavior from classes that are more general than the immediate class of the object, thus the
message implementation uses all handlers of this type from all the classes of an object. When only
the roles of the handlers specify which handlers get executed and in what order, the message is
said to be declaratively implemented. However, some message implementations may not fit this
model well. For example, the results of more than one primary handler may be needed. In cases
like this, the handlers themselves must take part in deciding which handlers get executed and in
what order. This is called the imperative technique. Around handlers provide imperative control
over all other types of handlers except more specific around handlers. Around handlers can change
the environment in which other handlers execute and modify the return value for the entire
message. A message implementation should use the declarative technique if at all possible because
this allows the handlers to be more independent and modular.

A defmessage-handler is comprised of seven elements: 1) a class name to which to attach the
handler (the class must have been previously defined), 2) a message name to which the handler
will respond, 3) an optional type (the default is primary), 4) an optional comment, 5) a list of
parameters that will be passed to the handler during execution, 6) an optional wildcard parameter
and 7) a series of expressions which are executed in order when the handler is called. The
return-value of a message-handler is the evaluation of the last expression in the body.

```
112 Section 9: CLIPS Object Oriented Language
```

Syntax

Defaults are in bold italics.

```
(defmessage-handler <class-name> <message-name>
[<handler-type>] [<comment>]
(<parameter>* [<wildcard-parameter>])
<action>*)
```

```
<handler-type> ::= around | before | primary | after
<parameter> ::= <single-field-variable>
<wildcard-parameter> ::= <multifield-variable>
```

Message-handlers are uniquely identified by class, name and type. Message-handlers are never
called directly. When the user sends a message to an object, CLIPS selects and orders the
applicable message-handlers attached to the object’s class(es) and then executes them. This
process is termed the message dispatch.

Example

```
CLIPS> (clear)
CLIPS> (defclass ORDER (is-a USER))
CLIPS>
(defmessage-handler ORDER delete before ()
(println "Deleting an instance of the class ORDER..."))
CLIPS>
(defmessage-handler USER delete after ()
(println "SYSTEM completed deletion of an instance."))
CLIPS> (watch instances)
CLIPS> (make-instance order of ORDER)
==> instance [order] of ORDER
[order]
CLIPS> (send [order] delete)
Deleting an instance of the class ORDER...
<== instance [order] of ORDER
SYSTEM completed deletion of an instance.
TRUE
CLIPS> (unwatch instances)
CLIPS>
```

#### 9.4.1 Message-handler Parameters

A message-handler may accept exactly or at least a specified number of arguments, depending on
whether a wildcard parameter is used or not. The regular parameters specify the minimum number
of arguments that must be passed to the handler. Each of these parameters may be referenced like
a normal single-field variable within the actions of the handler. If a wildcard parameter is present,
the handler may be passed any number of arguments greater than or equal to the minimum. If no
wildcard parameter is present, then the handler must be passed exactly the number of arguments
specified by the regular parameters. All arguments to a handler that do not correspond to a regular

```
CLIPS Basic Programming Guide 113
```

parameter are grouped into a multifield value that can be referenced by the wildcard parameter.
The standard CLIPS multifield functions, such as length$ and expand$, can be applied to the
wildcard parameter.

Handler parameters have no bearing on the applicability of a handler to a particular message.
However, if the number of arguments is inappropriate, a message execution error will be generated
when the handler is called. Thus, the number of arguments accepted should be consistent for all
message-handlers applicable to a particular message.

Example

```
CLIPS> (clear)
CLIPS>
(defclass LIST (is-a USER)
(multislot items))
CLIPS>
(defmessage-handler LIST insert (?index $?items)
(slot-direct-insert$ items ?index ?items))
CLIPS> (make-instance gl of LIST (items milk eggs cheese))
[gl]
CLIPS> (send [gl] insert 2 beer pretzels)
TRUE
CLIPS> (send [gl] get-items)
(milk beer pretzels eggs cheese)
CLIPS>
```

9.4.1.1 Active Instance Parameter

The term active instance refers to an instance that is responding to a message. All
message-handlers have an implicit parameter called ?self which binds the active instance for a
message. This parameter name is reserved and cannot be explicitly listed in the message-handler’s
parameters, nor can it be rebound within the body of a message-handler.

Example

```
CLIPS> (clear)
CLIPS>
(defclass RECTANGLE (is-a USER)
(slot width (default 0))
(slot height (default 0)))
CLIPS>
(defmessage-handler RECTANGLE area ()
(* (send ?self get-width) (send ?self get-height)))
CLIPS> (make-instance r of RECTANGLE (width 3) (height 5))
[r]
CLIPS> (send [r] area)
15
CLIPS>
```

```
114 Section 9: CLIPS Object Oriented Language
```

#### 9.4.2 Message-handler Actions

The body of a message-handler is a sequence of expressions that are executed in order when the
handler is called. The return value of the message-handler is the result of the evaluation of the last
expression in the body.

Handler actions may directly manipulate slots of the active instance. Normally, slots can only be
manipulated by sending the object slot-accessor messages. However, handlers are considered part
of the encapsulation of an object, and thus can directly view and change the slots of the object.
There are several functions which operate implicitly on the active instance (without the use of
messages) and can only be called from within a message-handler. These functions are discussed
in sections 12.17 and 12.19.

A shorthand notation is provided for accessing slots of the active instance from within a
message-handler.

Syntax

```
?self:<slot-name>
```

Example 1

```
CLIPS> (clear)
CLIPS>
(defclass PERSON (is-a USER)
(slot full-name)
(slot age)
(slot SSN))
CLIPS>
(defmessage-handler PERSON print-all-slots ()
(println ?self:full-name " " ?self:age " " ?self:SSN))
CLIPS>
(make-instance p1 of PERSON
(full-name "Jack Smith")
(age 37)
(SSN 673- 97 - 0035))
[p1]
CLIPS> (send [p1] print-all-slots)
Jack Smith 37 673- 97 - 0035
CLIPS>
```

Example 2

```
CLIPS> (clear)
CLIPS>
(defclass RECTANGLE (is-a USER)
(slot width (default 0))
(slot height (default 0)))
CLIPS>
(defmessage-handler RECTANGLE area ()
```

```
CLIPS Basic Programming Guide 115
```

```
(* ?self:width ?self:height)))
CLIPS> (make-instance r of RECTANGLE (width 3) (height 5))
[r]
CLIPS> (send [r] area)
15
CLIPS>
```

The bind function can also take advantage of this shorthand notation to set the value of a slot.

Syntax

```
(bind ?self:<slot-name> <value>*)
```

Example 1

```
CLIPS> (clear)
CLIPS>
(defclass PERSON (is-a USER)
(slot full-name)
(slot age (create-accessor ?NONE)))
CLIPS>
(defmessage-handler PERSON set-age (?value)
(bind ?self:age ?value))
CLIPS> (make-instance p1 of PERSON (full-name "Jack Smith"))
[p1]
CLIPS> (send [p1] set-age 37)
37
CLIPS> (send [p1] print)
[p1] of PERSON
(full-name "Jack Smith")
(age 37)
CLIPS>
```

Example 2

```
CLIPS> (clear)
CLIPS>
(defclass CAR (is-a USER)
(slot front-seat)
(multislot trunk)
(slot trunk-count))
CLIPS>
(defmessage-handler CAR put-items-in-car (?item $?rest)
(bind ?self:front-seat ?item)
(bind ?self:trunk ?rest)
(bind ?self:trunk-count (length$ ?rest)))
CLIPS> (make-instance Pinto of CAR)
[Pinto]
CLIPS> (send [Pinto] put-items-in-car bag-of-groceries
tire suitcase)
2
CLIPS> (send [Pinto] print)
[Pinto] of CAR
(front-seat bag-of-groceries)
```

```
116 Section 9: CLIPS Object Oriented Language
```

```
(trunk tire suitcase)
(trunk-count 2)
CLIPS>
```

Direct slot accesses are statically bound to the appropriate slot in the defclass when the
message-handler is defined. Care must be taken when these direct slot accesses can be executed as
the result of a message sent to an instance of a subclass of the class to which the message-handler
is attached. If the subclass has redefined the slot, the direct slot access contained in the
message-handler attached to the superclass will fail. That message-handler accesses the slot in the
superclass, not the subclass.

Example

```
CLIPS> (clear)
CLIPS>
(defclass ACCOUNT (is-a USER)
(slot account-# (create-accessor read)))
CLIPS>
(defclass SECURE-ACCOUNT (is-a ACCOUNT)
(slot account-# (create-accessor ?NONE)))
CLIPS> (make-instance sa of SECURE-ACCOUNT)
[sa]
CLIPS> (send [sa] get-account-#)
[MSGPASS3] Static reference to slot 'account-#' of class 'ACCOUNT' does not apply
to instance [sa] of class 'SECURE-ACCOUNT'.
[PRCCODE4] Execution halted during the actions of message-handler 'get-account-#'
primary in class 'ACCOUNT'
FALSE
CLIPS>
```

In order for direct slot accesses in a superclass message-handler to apply to new versions of the
slot in subclasses, the dynamic-put and dynamic-get functions must be used. However, the subclass
slot must have public visibility for this to work.

Example

```
CLIPS> (clear)
CLIPS>
(defclass ACCOUNT (is-a USER)
(slot account-# (create-accessor ?NONE)))
CLIPS>
(defmessage-handler ACCOUNT get-account-# ()
(dynamic-get account-#))
CLIPS>
(defclass SECURE-ACCOUNT (is-a ACCOUNT)
(slot account-# (visibility public)))
CLIPS> (make-instance sa of SECURE-ACCOUNT)
[sa]
CLIPS> (send [sa] get-account-#)
nil
CLIPS>
```

```
CLIPS Basic Programming Guide 117
```

#### 9.4.3 Daemons

Daemons are pieces of code which execute implicitly whenever some basic action is taken upon
an instance, such as initialization, deletion, or reading and writing of slots. All these basic actions
are implemented with primary handlers attached to the class of the instance. Daemons may be
easily implemented by defining other types of message-handlers, such as before or after, which
will recognize the same messages. These pieces of code will then be executed whenever the basic
actions are performed on the instance.

Example

```
CLIPS> (clear)
CLIPS> (defclass ORDER (is-a USER))
CLIPS>
(defmessage-handler ORDER init before ()
(println "Initializing a new instance of class ORDER..."))
CLIPS> (make-instance order of ORDER)
Initializing a new instance of class ORDER...
[order]
CLIPS>
```

#### 9.4.4 Predefined System Message-handlers.....................................................................

CLIPS defines eight primary message-handlers that are attached to the class USER. These handlers
cannot be deleted or modified.

9.4.4.1 Instance Initialization

Syntax

```
(defmessage-handler USER init primary ())
```

This handler is responsible for initializing instances with class default values after creation. The
make-instance and initialize-instance functions send the init message to an instance; the user
should never send this message directly. This handler is implemented using the init-slots function.
User-defined init handlers should not prevent the system message-handler from responding to an
init message.

Example

```
CLIPS> (clear)
CLIPS>
(defclass CAR (is-a USER)
(slot price (default 75000))
(slot model (default Corniche)))
CLIPS> (watch messages)
CLIPS> (watch message-handlers)
```

```
118 Section 9: CLIPS Object Oriented Language
```

```
CLIPS> (make-instance Rolls-Royce of CAR)
MSG >> create ED:1 (<Instance-Rolls-Royce>)
HND >> create primary in class USER
ED:1 (<Instance-Rolls-Royce>)
HND << create primary in class USER
ED:1 (<Instance-Rolls-Royce>)
MSG << create ED:1 (<Instance-Rolls-Royce>)
MSG >> init ED:1 (<Instance-Rolls-Royce>)
HND >> init primary in class USER
ED:1 (<Instance-Rolls-Royce>)
HND << init primary in class USER
ED:1 (<Instance-Rolls-Royce>)
MSG << init ED:1 (<Instance-Rolls-Royce>)
[Rolls-Royce]
CLIPS>
```

9.4.4.2 Instance Deletion

Syntax

```
(defmessage-handler USER delete primary ())
```

This handler is responsible for deleting an instance from the system. The user must directly send
a delete message to an instance. User-defined delete message-handlers should not prevent the
system message-handler from responding to a delete message. The handler returns the symbol
TRUE if the instance was successfully deleted, otherwise it returns the symbol FALSE.

Example

```
CLIPS> (send [Rolls-Royce] delete)
MSG >> delete ED:1 (<Instance-Rolls-Royce>)
HND >> delete primary in class USER
ED:1 (<Instance-Rolls-Royce>)
HND << delete primary in class USER
ED:1 (<Stale Instance-Rolls-Royce>)
MSG << delete ED:1 (<Stale Instance-Rolls-Royce>)
TRUE
CLIPS>
```

9.4.4.3 Instance Display

Syntax

```
(defmessage-handler USER print primary ())
```

This handler prints out slots and their values for an instance.

```
CLIPS Basic Programming Guide 119
```

Example

```
CLIPS> (make-instance Rolls-Royce of CAR)
MSG >> create ED:1 (<Instance-Rolls-Royce>)
HND >> create primary in class USER
ED:1 (<Instance-Rolls-Royce>)
HND << create primary in class USER
ED:1 (<Instance-Rolls-Royce>)
MSG << create ED:1 (<Instance-Rolls-Royce>)
MSG >> init ED:1 (<Instance-Rolls-Royce>)
HND >> init primary in class USER
ED:1 (<Instance-Rolls-Royce>)
HND << init primary in class USER
ED:1 (<Instance-Rolls-Royce>)
MSG << init ED:1 (<Instance-Rolls-Royce>)
[Rolls-Royce]
CLIPS> (send [Rolls-Royce] print)
MSG >> print ED:1 (<Instance-Rolls-Royce>)
HND >> print primary in class USER
ED:1 (<Instance-Rolls-Royce>)
[Rolls-Royce] of CAR
(price 75000)
(model Corniche)
HND << print primary in class USER
ED:1 (<Instance-Rolls-Royce>)
MSG << print ED:1 (<Instance-Rolls-Royce>)
CLIPS> (unwatch messages)
CLIPS. (unwatch message-handlers)
CLIPS>
```

9.4.4.4 Directly Modifying an Instance

Syntax

```
(defmessage-handler USER direct-modify primary
(?slot-override-expressions))
```

This handler modifies the slots of an instance directly rather than using put- override messages to
place the slot values. The slot-override expressions are passed as an EXTERNAL_ADDRESS data
object to the direct-modify handler. This message is used by the modify-instance and
active-modify-instance functions.

Example

The following around message-handler could be used to insure that all modify message
slot-overrides are handled using put- messages.

```
(defmessage-handler USER direct-modify around
(?overrides)
(send ?self message-modify ?overrides))
```

```
120 Section 9: CLIPS Object Oriented Language
```

9.4.4.5 Modifying an Instance using Messages

Syntax

```
(defmessage-handler USER message-modify primary
(?slot-override-expressions)
```

This handler modifies the slots of an instance using put- messages for each slot update. The
slot-override expressions are passed as an EXTERNAL_ADDRESS data object to the
message-modify handler. This message is used by the message-modify-instance and
active-message-modify-instance functions.

9.4.4.6 Directly Duplicating an Instance

Syntax

```
(defmessage-handler USER direct-duplicate primary
(?new-instance-name ?slot-override-expressions))
```

This handler duplicates an instance without using put- messages to assign the slot-overrides. Slot
values from the original instance and slot overrides are directly copied. If the name of the new
instance created matches a currently existing instance-name, then the currently existing instance
is deleted without use of a message. The slot-override expressions are passed as an
EXTERNAL_ADDRESS data object to the direct-duplicate handler. This message is used by the
duplicate-instance and active-duplicate-instance functions.

Example

The following around message-handler could be used to insure that all duplicate message
slot-overrides are handled using put- messages.

```
(defmessage-handler USER direct-duplicate around
(?new-name ?overrides)
(send ?self message-duplicate ?new-name ?overrides))
```

9.4.4.7 Duplicating an Instance using Messages

Syntax

```
(defmessage-handler USER message-duplicate primary
(?new-instance-name ?slot-override-expressions)
```

This handler duplicates an instance using messages. Slot values from the original instance and slot
overrides are copied using put- and get- messages. If the name of the new instance created matches
a currently existing instance-name, then the currently existing instance is deleted using a delete
message. After creation, the new instance is sent a create message and then an init message. The

```
CLIPS Basic Programming Guide 121
```

slot-override expressions are passed as an EXTERNAL_ADDRESS data object to the
message-duplicate handler. This message is used by the message-duplicate-instance and
active-message-duplicate-instance functions.

9.4.4.8 Instance Creation

Syntax

```
(defmessage-handler USER create primary ())
```

This handler is called after an instance is created, but before any slot initialization has occurred.
The newly created instance is sent a create message. This handler performs no actions—It is
provided so that instance creation can be detected by user-defined message-handlers. The handler
returns the symbol TRUE if the instance was successfully created, otherwise it returns the symbol
FALSE.

### 9.5 Message Dispatch

When a message is sent to an object using the send function, CLIPS examines the class precedence
list of the active instance’s class to determine a complete set of message-handlers which are
applicable to the message. CLIPS uses the roles (around, before, primary or after) and specificity
of these message-handlers to establish an ordering and then executes them. A handler that is
attached to a subclass of another message-handler’s class is said to be more specific. This entire
process is referred to as the message dispatch. Shown following is a flow diagram summary:

```
122 Section 9: CLIPS Object Oriented Language
```

The solid arrows indicate automatic control transfer by the message dispatch system. The dashed
arrows indicate control transfer that can only be accomplished by the use or lack of the use of
call-next-handler (or override-next-handler).

#### 9.5.1 Applicability of Message-handlers

A message-handler is applicable to a message if its name matches the message, and it is attached
to a class which is in the class precedence list of the class of the instance receiving the message.

```
DONE: Return control and values to caller.
```

```
START: Input is a list of applicable message-handlers.
```

```
AROUND STEP: Are there any uncalled around handlers?
YES: Call the most specific uncalled around handler.
If the body uses call-next-handler, repeat this step.
Else go to DONE.
When body returns, return its values to caller.
NO: Proceed to BEFORE STEP.
```

```
BEFORE STEP: Are there any uncalled before handlers?
YES: Call the most specific uncalled before handler.
When body returns, repeat this step.
NO: Proceed to PRIMARY STEP
```

```
AFTER STEP: Are there any uncalled after handlers?
YES: Call the least specific uncalled after handler.
When body returns, repeat this step.
NO: Proceed to DONE.
```

```
PRIMARY STEP: Are there any uncalled primary handlers?
YES: Call the most specific uncalled primary handler.
If the body uses call-next-handler, repeat this step.
When body returns, return its values to caller.
NO: Proceed to AFTER STEP.
```

```
CLIPS Basic Programming Guide 123
```

#### 9.5.2 Message-handler Precedence

The set of all applicable message-handlers are sorted into four groups according to role, and these
four groups are further sorted by class specificity. The around, before, and primary handlers are
ordered from most specific to most general, whereas after handlers are ordered from most general
to most specific.

The order of execution is as follows: 1) around handlers begin execution from most specific to
most general (each around handler must explicitly allow execution of other handlers), 2) before
handlers execute (one after the other) from most specific to most general 3) primary handlers begin
execution from most specific to most general (more specific primary handlers must explicitly allow
execution of more general ones), 4) primary handlers finish execution from most general to most
specific, 5) after handlers execute (one after the other) from most general to most specific and 6)
around handlers finish execution from most general to most specific.

There must be at least one applicable primary handler for a message, or a message execution error
will be generated.

#### 9.5.3 Shadowed Message-handlers

When one handler must be called by another handler in order to be executed, the first handler is
said to be shadowed by the second. An around handler shadows all handlers except more specific
around handlers. A primary handler shadows all more general primary handlers.

Messages should be implemented using the declarative technique, if possible. Only the handler
roles will dictate which handlers get executed; only before and after handlers and the most specific
primary handler are used. This allows each handler for a message to be completely independent of
the other message-handlers. However, if around handlers or shadowed primary handlers are
necessary, then the handlers must explicitly take part in the message dispatch by calling other
handlers they are shadowing. This is called the imperative technique. The call-next-handler and
override-next-handler functions allow a handler to execute the handler it is shadowing. A handler
can call the same shadowed handler multiple times.

Example

```
(defmessage-handler USER my-message around ()
(call-next-handler))
```

```
(defmessage-handler USER my-message before ())
```

```
(defmessage-handler USER my-message ()
(call-next-handler))
```

```
(defmessage-handler USER my-message after ())
```

```
124 Section 9: CLIPS Object Oriented Language
```

```
(defmessage-handler OBJECT my-message around ()
(call-next-handler))
```

```
(defmessage-handler OBJECT my-message before ())
```

```
(defmessage-handler OBJECT my-message ())
```

```
(defmessage-handler OBJECT my-message after ())
```

For a message sent to an instance of a class which inherits from USER, the following diagram
illustrates the order of execution for the handlers attached to the classes USER and OBJECT. The
brackets indicate where a particular handler begins and ends execution. Handlers enclosed within
a bracket are shadowed.

#### 9.5.4 Message Execution Errors

If an error occurs at any time during the execution of a message-handler, any currently executing
handlers will be aborted, any handlers which have not yet started execution will be ignored, and
the send function will return the symbol FALSE.

A lack of applicable of primary message-handlers and a handler being called with the wrong
number of arguments are common message execution errors.

#### 9.5.5 Message Return Value

The return value of call to the send function is the return value of the most specific around handler,
or the most specific primary handler if there are no around handlers. The return value of a handler
is the result of the evaluation of the last action in the handler.

```
USER around begin
```

```
USER around end
```

```
OBJECT around begin
```

```
OBJECT around end
```

```
USER before
```

```
USER after
```

```
OBJECT before
```

```
OBJECT after
```

```
USER primary begin
```

```
USER primary end
```

```
OBJECT primary
```

```
CLIPS Basic Programming Guide 125
```

The return values of the before and after handlers are ignored; they are for side-effects only. An
around handler can choose to ignore or capture the return value of the next most specific around
or primary handler. A primary handler can choose to ignore or capture the return value of a more
general primary handler.

### 9.6 Manipulating Instances

Objects are manipulated by sending them messages. This is achieved by using the send function,
which takes as arguments the destination object for the message, the message itself, and any
arguments which are to be passed to handlers.

Syntax

```
(send <object-expression>
<message-name-expression> <expression>*)
```

The slots of an object may be read or set directly only within the body of a message-handler that
is executing on behalf of a message that was sent to that object. This is how COOL implements
the notion of encapsulation. Any action performed on an object by an external source, such as a
rule or function, must be done with messages. There are two major exceptions: 1) objects which
are not instances of user-defined classes (floating-point and integer numbers, symbols, strings,
multifield values, fact-addresses and external-addresses) can be manipulated in the standard
non-OOP manner and 2) creation and initialization of an instance of a user-defined class are
performed via the make-instance function.

#### 9.6.1 Creating Instances

Like facts, instances of user-defined classes must be explicitly created by the user. Likewise, all
instances are deleted during the reset command, and they can be loaded and saved similarly to
facts. All operations involving instances require message-passing using the send function except
for creation, since the object does not yet exist. A function called make-instance is used to create
and initialize a new instance. This function implicitly sends first a create message and then an
initialization message to the new object after allocation. The user can customize instance
initialization with daemons. The make-instance function also allows slot-overrides to change any
predefined initialization for a particular instance. The make-instance function automatically
delays all object pattern-matching activities for rules until all slot overrides have been processed.
The active-make-instance function can be used if delayed pattern-matching is not desired. The
active-make-instance function remembers the current state of delayed pattern-matching,
explicitly turns delay on, and then restores it to its previous state once all slot overrides have been
processed.

Syntax

```
(make-instance <instance-definition>)
```

```
126 Section 9: CLIPS Object Oriented Language
```

```
(active-make-instance <instance-definition>)
```

```
<instance-definition> ::= [<instance-name-expression>] of
<class-name-expression>
<slot-override>*
<slot-override> ::= (<slot-name-expression>
<expression>*)
```

The return value of make-instance is the name of the new instance on success or the symbol
FALSE on failure. The evaluation of <instance-name-expression> can either be an instance-name
or a symbol. If <instance-name-expression> is not specified, then the gensym\* function will be
called to generate the instance-name.

The make-instance function performs the following steps in order:

```
1) If an instance of the specified name already exists, that instance receives a delete message,
e.g. (send <instance-name> delete). If this fails for any reason, the new instance creation is
aborted. Normally, the handler attached to class USER will respond to this message.
```

```
2) A new and uninitialized instance of the specified class is created with the specified name.
```

```
3) The new instance receives the create message, e.g. (send <instance-name> create). Normally,
the handler attached to class USER will respond to this, although it performs no actions.
```

```
4) All slot-overrides are immediately evaluated and placed via put- messages, e.g. (send
<instance-name> put-<slot-name> <expression>*). If there are any errors, the new instance
is deleted.
```

```
5) The new instance receives the init message, e.g. (send <instance-name> init). Normally, the
handler attached to class USER will respond to this message. This handler calls the init-slots
function. This function uses defaults from the class definition (if any) for any slots which do
not have slot-overrides. The class defaults are placed directly without the use of messages. If
there are any errors, the new instance is deleted.
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass POINT (is-a USER)
(slot x (type INTEGER))
(slot y (type INTEGER)))
CLIPS>
(defmessage-handler POINT put-x before (?value)
(println "Slot x set with message."))
CLIPS>
(defmessage-handler POINT delete after ()
(println "Old instance deleted."))
CLIPS> (make-instance p of POINT)
[p]
```

```
CLIPS Basic Programming Guide 127
```

```
CLIPS> (send [p] print)
[p] of POINT
(x 0)
(y 0)
CLIPS> (make-instance [p] of POINT (x 3))
Old instance deleted.
Slot x set with message.
[p]
CLIPS> (send [a] print)
[MSGPASS2] No such instance [a] in function 'send'.
FALSE
CLIPS> (send [p] print)
[p] of POINT
(x 3)
(y 0)
CLIPS> (send [p] delete)
Old instance deleted.
TRUE
CLIPS>
```

9.6.1.1 Definstances Construct

Similar to deffacts, the definstances construct allows the specification of instances which will be
created every time the reset command is executed. On every reset all current instances receive a
delete message, and the equivalent of a make-instance function call is made for every instance
specified in definstances constructs.

Syntax

```
(definstances <definstances-name> [active] [<comment>]
<instance-template>*)
<instance-template> ::= (<instance-definition>)
```

A definstances cannot use classes that have not been previously defined. The instances of a
definstances are created in order, and if any individual creation fails, the remainder of the
definstances will be aborted. Normally, definstances just use the make-instance function (which
means delayed Rete activity) to create the instances. However, if this is not desired, then the active
keyword can be specified after the definstances name so that the active-make-instance function
will be used.

Example

```
CLIPS> (clear)
CLIPS>
(defclass POINT (is-a USER)
(slot x (type INTEGER))
(slot y (type INTEGER)))
CLIPS>
(definstances POINTS
(p1 of POINT (x 3) (y 2))
```

```
128 Section 9: CLIPS Object Oriented Language
```

```
(of POINT (x 7)))
CLIPS> (watch instances)
CLIPS> (reset)
==> instance [p1] of POINT
==> instance [gen1] of POINT
CLIPS> (reset)
<== instance [p1] of POINT
<== instance [gen1] of POINT
==> instance [p1] of POINT
==> instance [gen2] of POINT
CLIPS> (unwatch instances)
CLIPS>
```

#### 9.6.2 Reinitializing Existing Instances.............................................................................

The initialize-instance function provides the ability to reinitialize an existing instance with class
defaults and new slot-overrides. The return value of initialize-instance is the name of the instance
on success or the symbol FALSE on failure. The evaluation of <instance-name-expression> can
either be an instance-name, instance-address, or a symbol. The initialize-instance function
automatically delays all object pattern-matching activities for rules until all slot overrides have
been processed. The active-initialize-instance function can be used if delayed pattern-matching
is not desired.

Syntax

```
(initialize-instance <instance-name-expression>
<slot-override>*)
```

The initialize-instance function performs the following steps in order:

```
1) All slot-overrides are immediately evaluated and placed via put- messages, e.g. (send
<instance-name> put-<slot-name> <expression>*).
```

```
2) The instance receives the init message, e.g. (send <instance-name> init). Normally, the
handler attached to class USER will respond to this message. This handler calls the init-slots
function. This function uses defaults from the class definition (if any) for any slots that do not
have slot-overrides. The class defaults are placed directly without the use of messages.
```

If no slot-override or class default specifies the value of a slot, that value will remain the same.
Empty class default values allow initialize-instance to clear a slot.

If an error occurs, the instance will not be deleted, but the slot values may be in an inconsistent
state.

Example

```
CLIPS> (clear)
```

```
CLIPS Basic Programming Guide 129
```

```
CLIPS>
(defclass POINT (is-a USER)
(slot x (type INTEGER))
(slot y (type INTEGER))
(slot z (type INTEGER)))
CLIPS> (make-instance p of POINT (y 100))
[p]
CLIPS> (send [p] print)
[p] of POINT
(x 0)
(y 100)
(z 0)
CLIPS> (send [p] put-x 65)
65
CLIPS> (send [p] put-y 17)
17
CLIPS> (send [p] put-z -30)
```

- 30
  CLIPS> (send [p] print)
  [p] of POINT
  (x 65)
  (y 17)
  (z -30)
  CLIPS> (initialize-instance p)
  [p]
  CLIPS> (send [p] print)
  [p] of POINT
  (x 0)
  (y 0)
  (z 0)
  CLIPS>

#### 9.6.3 Reading Slots

Sources external to an object, such as a rule or deffunction, can read an object’s slots only by
sending the object a message. Message-handlers executing on the behalf of an object can either
use messages or direct access to read the object’s slots. Several functions also exist which operate
implicitly on the active instance for a message that can only be called by message-handlers, such
as dynamic-get.

Example

```
CLIPS> (clear)
CLIPS>
(defclass PERSON (is-a USER)
(slot full-name)
(slot age))
CLIPS> (make-instance p of PERSON (full-name "Jack Smith") (age 37))
[p]
CLIPS> (send [p] get-full-name)
"Jack Smith"
CLIPS> (send [p] get-age)
```

```
130 Section 9: CLIPS Object Oriented Language
```

```
37
CLIPS>
```

#### 9.6.4 Setting Slots

Sources external to an object, such as a rule or deffunction, can write an object’s slots only by
sending the object a message. Several functions also exist which operate implicitly on the active
instance for a message that can only be called by message-handlers, such as dynamic-put. The
bind function can also be used to set a slot's value from within a message-handler.

Example

```
CLIPS> (clear)
CLIPS>
(defclass PERSON (is-a USER)
(slot full-name)
(slot age))
CLIPS> (make-instance p of PERSON (full-name "Jack Smith") (age 37))
[p]
CLIPS> (send [p] put-age 38)
38
CLIPS> (send [p] print)
[p] of PERSON
(full-name "Jack Smith")
(age 38)
CLIPS>
```

#### 9.6.5 Deleting Instances

Sending the delete message to an instance removes it from the system. Within a message-handler,
the delete-instance function can be used to delete the active instance for a message.

Syntax

```
(send <instance> delete)
```

#### 9.6.6 Delayed Pattern-Matching When Manipulating Instances

While creating, modifying, or deleting instances, the object-pattern-match-delay function delays
pattern-matching activities for rules until after all of the manipulations have been made. This
function acts identically to the progn function, however, any actions that could affect object
pattern-matching for rules are delayed until the function is exited. This function’s primary purpose
is to provide some control over performance.

Syntax

```
(object-pattern-match-delay <action>*)
```

```
CLIPS Basic Programming Guide 131
```

Example

```
CLIPS> (clear)
CLIPS> (defclass ORDER (is-a USER))
CLIPS>
(defrule match-order
(object (is-a ORDER))
=>)
CLIPS> (make-instance order of ORDER)
[order]
CLIPS> (agenda)
0 match-order: [order]
For a total of 1 activation.
CLIPS> (make-instance another-order of ORDER)
[another-order]
CLIPS> (agenda)
0 match-order: [another-order]
0 match-order: [order]
For a total of 2 activations.
CLIPS>
(object-pattern-match-delay
(make-instance third-order of ORDER)
(println "After third order")
(agenda)
(make-instance fourth-order of ORDER)
(println "After fourth order")
(agenda))
After third order
0 match-order: [another-order]
0 match-order: [order]
For a total of 2 activations.
After fourth order
0 match-order: [another-order]
0 match-order: [order]
For a total of 2 activations.
CLIPS> (agenda)
0 match-order: [fourth-order]
0 match-order: [third-order]
0 match-order: [another-order]
0 match-order: [order]
For a total of 4 activations.
CLIPS>
```

#### 9.6.7 Modifying Instances................................................................................................

Four functions are provided for modifying instances. These functions allow instance slot updates
to be performed in blocks without requiring a series of put- messages. Each of these functions
returns the symbol TRUE if successful, otherwise the symbol FALSE is returned.

```
132 Section 9: CLIPS Object Oriented Language
```

9.6.7.1 Directly Modifying an Instance with Delayed Pattern-Matching

The modify-instance function uses the direct-modify message to change the values of the
instance. Object pattern-matching is delayed until all of the slot modifications have been
performed.

Syntax

```
(modify-instance <instance> <slot-override>*)
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass POINT (is-a USER)
(slot x (type INTEGER))
(slot y (type INTEGER)))
CLIPS> (make-instance p of POINT)
[p]
CLIPS> (watch all)
CLIPS> (modify-instance p (x 3))
MSG >> direct-modify ED:1 (<Instance-p> <Pointer-C-0x608000252c00>)
HND >> direct-modify primary in class USER
ED:1 (<Instance-p> <Pointer-C-0x608000252c00>)
::= local slot x in instance p <- 3
HND << direct-modify primary in class USER
ED:1 (<Instance-p> <Pointer-C-0x608000252c00>)
MSG << direct-modify ED:1 (<Instance-p> <Pointer-C-0x608000252c00>)
TRUE
CLIPS> (unwatch all)
CLIPS>
```

9.6.7.2 Directly Modifying an Instance with Immediate Pattern-Matching

The active-modify-instance function uses the direct-modify message to change the values of the
instance. Object pattern-matching occurs as slot modifications are being performed.

Syntax

```
(active-modify-instance <instance> <slot-override>*)
```

9.6.7.3 Modifying an Instance using Messages with Delayed Pattern-Matching

The message-modify-instance function uses the message-modify message to change the values
of the instance. Object pattern-matching is delayed until all of the slot modifications have been
performed.

```
CLIPS Basic Programming Guide 133
```

Syntax

```
(message-modify-instance <instance> <slot-override>*)
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass POINT (is-a USER)
(slot x (type INTEGER))
(slot y (type INTEGER)))
CLIPS> (make-instance p of POINT)
[p]
CLIPS> (watch all)
CLIPS> (message-modify-instance p (x 4))
MSG >> message-modify ED:1 (<Instance-p> <Pointer-C-0x608000252c60>)
HND >> message-modify primary in class USER
ED:1 (<Instance-p> <Pointer-C-0x608000252c60>)
MSG >> put-x ED:2 (<Instance-p> 4)
HND >> put-x primary in class POINT
ED:2 (<Instance-p> 4)
::= local slot x in instance p <- 4
HND << put-x primary in class POINT
ED:2 (<Instance-p> 4)
MSG << put-x ED:2 (<Instance-p> 4)
HND << message-modify primary in class USER
ED:1 (<Instance-p> <Pointer-C-0x608000252c60>)
MSG << message-modify ED:1 (<Instance-p> <Pointer-C-0x608000252c60>)
TRUE
CLIPS> (unwatch all)
CLIPS>
```

9.6.7.4 Modifying an Instance using Messages with Immediate Pattern-Matching

The active-message-modify-instance function uses the message-modify message to change the
values of the instance. Object pattern-matching occurs as slot modifications are being performed.

Syntax

```
(active-message-modify-instance <instance> <slot-override>*)
```

#### 9.6.8 Duplicating Instances

Four functions are provided for duplicating instances. These functions allow instance duplication
and slot updates to be performed in blocks without requiring a series of put- messages. Each of
these functions return the instance-name of the new duplicated instance if successful, otherwise
the symbol FALSE is returned.

```
134 Section 9: CLIPS Object Oriented Language
```

Each of the duplicate functions can optionally specify the name of the instance to which the old
instance will be copied. If the name is not specified, the function will generate the name using the
gensym\* function. If the target instance already exists, it will be deleted directly or with a delete
message depending on which function was called.

9.6.8.1 Directly Duplicating an Instance with Delayed Pattern-Matching

The duplicate-instance function uses the direct-duplicate message to change the values of the
instance. Object pattern-matching is delayed until all of the slot modifications have been
performed.

Syntax

```
(duplicate-instance <instance> [to <instance-name>]
<slot-override>*)
```

Example

```
CLIPS> (clear)
CLIPS> (setgen 1)
1
CLIPS>
(defclass POINT (is-a USER)
(slot x (type INTEGER))
(slot y (type INTEGER)))
CLIPS> (make-instance p of POINT (x 3) (y 5))
[p]
CLIPS> (watch all)
CLIPS> (duplicate-instance p)
MSG >> direct-duplicate ED:1 (<Instance-p> gen1 <Pointer-C-0x0>)
HND >> direct-duplicate primary in class USER
ED:1 (<Instance-p> gen1 <Pointer-C-0x0>)
==> instance [gen1] of POINT
::= local slot x in instance gen1 <- 3
::= local slot y in instance gen1 <- 5
HND << direct-duplicate primary in class USER
ED:1 (<Instance-p> gen1 <Pointer-C-0x0>)
MSG << direct-duplicate ED:1 (<Instance-p> gen1 <Pointer-C-0x0>)
[gen1]
CLIPS> (unwatch all)
CLIPS>
```

9.6.8.2 Directly Duplicating an Instance with Immediate Pattern-Matching

The active-duplicate-instance function uses the direct-duplicate message to change the values
of the instance. Object pattern-matching occurs as slot modifications are being performed.

```
CLIPS Basic Programming Guide 135
```

Syntax

```
(active-duplicate-instance <instance> [to <instance-name>]
<slot-override>*)
```

9.6.8.3 Duplicating an Instance using Messages with Delayed Pattern-Matching

The message-duplicate-instance function uses the message-duplicate message to change the
values of the instance. Object pattern-matching is delayed until all of the slot modifications have
been performed.

Syntax

```
(message-duplicate-instance <instance> [to <instance-name>]
<slot-override>*)
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass POINT (is-a USER)
(slot x (type INTEGER))
(slot y (type INTEGER)))
CLIPS> (make-instance p1 of POINT (x 3) (y 4))
[p1]
CLIPS> (make-instance p2 of POINT)
[p2]
CLIPS> (watch all)
CLIPS> (message-duplicate-instance p1 to p2 (y 6))
MSG >> message-duplicate ED:1 (<Instance-p1> p2 <Pointer-C-0x60c00005a850>)
HND >> message-duplicate primary in class USER
ED:1 (<Instance-p1> p2 <Pointer-C-0x60c00005a850>)
MSG >> delete ED:2 (<Instance-p2>)
HND >> delete primary in class USER
ED:2 (<Instance-p2>)
<== instance [p2] of POINT
HND << delete primary in class USER
ED:2 (<Stale Instance-p2>)
MSG << delete ED:2 (<Stale Instance-p2>)
==> instance [p2] of POINT
MSG >> create ED:2 (<Instance-p2>)
HND >> create primary in class USER
ED:2 (<Instance-p2>)
HND << create primary in class USER
ED:2 (<Instance-p2>)
MSG << create ED:2 (<Instance-p2>)
MSG >> put-y ED:2 (<Instance-p2> 6)
HND >> put-y primary in class POINT
ED:2 (<Instance-p2> 6)
::= local slot y in instance p2 <- 6
HND << put-y primary in class POINT
ED:2 (<Instance-p2> 6)
```

```
136 Section 9: CLIPS Object Oriented Language
```

```
MSG << put-y ED:2 (<Instance-p2> 6)
MSG >> put-x ED:2 (<Instance-p2> 3)
HND >> put-x primary in class POINT
ED:2 (<Instance-p2> 3)
::= local slot x in instance p2 <- 3
HND << put-x primary in class POINT
ED:2 (<Instance-p2> 3)
MSG << put-x ED:2 (<Instance-p2> 3)
MSG >> init ED:2 (<Instance-p2>)
HND >> init primary in class USER
ED:2 (<Instance-p2>)
HND << init primary in class USER
ED:2 (<Instance-p2>)
MSG << init ED:2 (<Instance-p2>)
HND << message-duplicate primary in class USER
ED:1 (<Instance-p1> p2 <Pointer-C-0x60c00005a850>)
MSG << message-duplicate ED:1 (<Instance-p1> p2 <Pointer-C-0x60c00005a850>)
[p2]
CLIPS> (unwatch all)
CLIPS>
```

9.6.8.4 Duplicating an Instance using Messages with Immediate Pattern-Matching

The active-message-duplicate-instance function uses the message-duplicate message to change
the values of the instance. Object pattern-matching occurs as slot modifications are being
performed.

Syntax

```
(active-message-duplicate-instance <instance>
[to <instance-name>]
<slot-override>*)
```

### 9.7 Instance-set Queries and Distributed Actions

COOL provides a useful query system for determining and performing actions on sets of instances
of user-defined classes that satisfy user-defined queries. The instance query system in COOL
provides six functions, each of which operate on instance-sets determined by user-defined criteria:

```
CLIPS Basic Programming Guide 137
```

```
Function Purpose
```

```
any-instancep Determines if one or more instancesatisfy a query - sets
```

```
find-instance Returns the first instancequery - set that satisfies a
```

```
find-all-instances Groups and returns all instancesatisfy a query - sets which
```

```
do-for-instance Performs an action for the first instancewhich satisfies a query - set
```

```
do-for-all-instances Performs an action for every instancewhich satisfies a query as they are found-set
```

```
delayed-do-for-all-instances Groups all instanceand then iterates an action over this group-sets which satisfy a query
```

Explanations on how to form instance-set templates, queries and actions immediately follow, for
these definitions are common to all of the query functions. The specific details of each query
function will then be given. The following is a complete example of an instance-set query function:

Example

For all of the examples in this section, assume that the following commands have already been
entered:

Example

```
CLIPS>
(defclass PERSON (is-a USER)
(role abstract)
(slot sex (access read-only)
(storage shared))
(slot age (type NUMBER)
(create-accessor ?NONE)
(visibility public)))
```

```
CLIPS>
(do-for-all-instances
((?car1 MASERATI BMW) (?car2 ROLLS-ROYCE))
(> ?car1:price (* 1.5 ?car2:price))
(printout t ?car1:name crlf))
[Albert-Maserati]
CLIPS>
```

```
Instance-set template
Instance-set query
Instance-set distributed action
```

```
Instance-set member variables
```

```
Instance-set member class restrictions
```

138 Section 9: CLIPS Object Oriented Language

```
CLIPS>
(defmessage-handler PERSON put-age (?value)
(dynamic-put age ?value))
CLIPS>
(defclass FEMALE (is-a PERSON)
(role abstract)
(slot sex (source composite)
(default female)))
CLIPS>
(defclass MALE (is-a PERSON)
(role abstract)
(slot sex (source composite)
(default male)))
CLIPS>
(defclass GIRL (is-a FEMALE)
(role concrete)
(slot age (source composite)
(default 4)
(range 0.0 17.9)))
CLIPS>
(defclass WOMAN (is-a FEMALE)
(role concrete)
(slot age (source composite)
(default 25)
(range 18.0 100.0)))
CLIPS>
(defclass BOY (is-a MALE)
(role concrete)
(slot age (source composite)
(default 4)
(range 0.0 17.9)))
CLIPS>
(defclass MAN (is-a MALE)
(role concrete)
(slot age (source composite)
(default 25)
(range 18.0 100.0)))
CLIPS>
(definstances PEOPLE
(Man-1 of MAN (age 18))
(Man-2 of MAN (age 60))
(Woman-1 of WOMAN (age 18))
(Woman-2 of WOMAN (age 60))
(Woman-3 of WOMAN)
(Boy-1 of BOY (age 8))
(Boy-2 of BOY)
(Boy-3 of BOY)
(Boy-4 of BOY)
(Girl-1 of GIRL (age 8))
(Girl-2 of GIRL))
CLIPS> (reset)
CLIPS>
```

```
CLIPS Basic Programming Guide 139
```

#### 9.7.1 Instance-set Definition

An instance-set is an ordered collection of instances. Each instance-set member is an instance of
a set of classes, called class restrictions, defined by the user. The class restrictions can be different
for each instance-set member. The query functions use instance-set templates to generate
instance-sets. An instance-set template is a set of instance-set member variables and their
associated class restrictions. Instance-set member variables reference the corresponding members
in each instance-set that matches a template. Variables may be used to specify the classes for the
instance-set template, but if the constant names of the classes are specified, the classes must
already be defined. Module specifiers may be included with the class names; the classes need not
be in scope of the current module.

Syntax

```
<instance-set-template>
::= (<instance-set-member-template>+)
<instance-set-member-template>
::= (<instance-set-member-variable> <class-restrictions>)
<instance-set-member-variable> ::= <single-field-variable>
<class-restrictions> ::= <class-name-expression>+
```

Example

One instance-set template might be the ordered pairs of boys or men and girls or women.

```
((?man-or-boy BOY MAN) (?woman-or-girl GIRL WOMAN))
```

This instance-set template could have been written equivalently:

```
((?man-or-boy MALE) (?woman-or-girl FEMALE))
```

Instance-set member variables (e.g. ?man-or-boy) are bound to instance-names.

#### 9.7.2 Instance-set Determination

COOL uses straightforward permutations to generate instance-sets that match an instance-set
template from the actual instances in the system. The rules are as follows:

```
1) When there is more than one member in an instance-set template, vary the rightmost members
first.
```

```
2) When there is more than one class that an instance-set member can be, iterate through the
classes from left to right.
```

```
3) Examine instances of a class in the order that they were defined.
```

```
140 Section 9: CLIPS Object Oriented Language
```

```
a) Recursively examine instances of subclasses in the order that the subclasses were defined.
If the specified query class was in scope of the current module, then only subclasses that
are also in scope will be examined. Otherwise, only subclasses that are in scope of the
module to which the query class belongs will be examined.
```

Example

For the instance-set template given in section 9.7.1, thirty instance-sets would be generated in the
following order:

1. [Boy-1] [Girl-1]
2. [Boy-1] [Girl-2]
3. [Boy-1] [Woman-1]
4. [Boy-1] [Woman-2]
5. [Boy-1] [Woman-3]
6. [Boy-2] [Girl-1]
7. [Boy-2] [Girl-2]
8. [Boy-2] [Woman-1]
9. [Boy-2] [Woman-2]
10. [Boy-2] [Woman-3]
11. [Boy-3] [Girl-1]
12. [Boy-3] [Girl-2]
    13 [Boy-3] [Woman-1]
13. [Boy-3] [Woman-2]
    1 5. [Boy-3] [Woman-3] 16. [Boy-4] [Girl-1] 17. [Boy-4] [Girl-2] 18. [Boy-4] [Woman-1] 19. [Boy-4] [Woman-2] 20. [Boy-4] [Woman-3] 21. [Man-1] [Girl-1] 22. [Man-1] [Girl-2] 23. [Man-1] [Woman-1] 24. [Man-1] [Woman-2] 25. [Man-1] [Woman-3] 26. [Man-2] [Girl-1] 27. [Man-2] [Girl-2] 28. [Man-2] [Woman-1] 29. [Man-2] [Woman-2] 30. [Man-2] [Woman-3]

Example

Consider the following instance-set template:

```
((?f1 FEMALE) (?f2 FEMALE))
```

Twenty-five instance-sets would be generated in the following order:

1. [Girl-1] [Girl-1]
2. [Girl-1] [Girl-2]
3. [Girl-1] [Woman-1]
4. [Girl-1] [Woman-2]
5. [Girl-1] [Woman-3]
6. [Girl-2] [Girl-1]
7. [Girl-2] [Girl-2]
8. [Girl-2] [Woman-1]
9. [Girl-2] [Woman-2] 10.[Girl-2] [Woman-3] 11.[Woman-1] [Girl-1] 12.[Woman-1] [Girl-2] 13.[Woman-1] [Woman-1]

```
14.[Woman-1] [Woman-2]
15.[Woman-1] [Woman-3]
16.[Woman-2] [Girl-1]
17.[Woman-2] [Girl-2]
18.[Woman-2] [Woman-1]
19.[Woman-2] [Woman-2]
20.[Woman-2] [Woman-3]
21.[Woman-3] [Girl-1]
22.[Woman-3] [Girl-2]
23.[Woman-3] [Woman-1]
24.[Woman-3] [Woman-2]
25.[Woman-3] [Woman-3]
```

The instances of class GIRL are examined before the instances of class WOMAN because GIRL
was defined before WOMAN.

```
CLIPS Basic Programming Guide 141
```

#### 9.7.3 Query Definition

A query is a user-defined boolean expression applied to an instance-set to determine if the
instance-set meets further user-defined restrictions. If the evaluation of this expression for an
instance-set is anything but the symbol FALSE, the instance-set is said to satisfy the query.

Syntax

```
<query> ::= <boolean-expression>
```

Example

Continuing the previous example, one query might be that the two instances in an ordered pair
have the same age.

```
(= (send ?man-or-boy get-age) (send ?woman-or-girl get-age))
```

Within a query, slots of instance-set members can be directly read with a shorthand notation similar
to that used in message-handlers. If message-passing is not explicitly required for reading a slot
(i.e. there are no accessor daemons for reads), then this second method of slot access should be
used, for it gives a significant performance benefit.

Syntax

```
<instance-set-member-variable>:<slot-name>
```

Example

The previous example could be rewritten as:

```
(= ?man-or-boy:age ?woman-or-girl:age)
```

Since only instance-sets that satisfy a query are of interest, and the query is evaluated for all
possible instance-sets, the query should not have any side-effects.

#### 9.7.4 Distributed Action Definition

A distributed action is an expression evaluated for each instance-set which satisfies a query.
Unlike queries, distributed actions must use messages to read slots of instance-set members.

Action Syntax

```
<action> ::= <expression>
```

```
142 Section 9: CLIPS Object Oriented Language
```

Example

Continuing the previous example, one distributed action might be to simply print out the ordered
pair to the screen.

```
(println "(" ?man-or-boy "," ?woman-or-girl ")")
```

#### 9.7.5 Scope in Instance-set Query Functions

An instance-set query function can be called from anywhere that a regular function can be called.
If a variable from an outer scope is not masked by an instance-set member variable, then that
variable may be referenced within the query and action. In addition, rebinding variables within an
instance-set function action is allowed. However, attempts to rebind instance-set member variables
will generate errors. Binding variables is not allowed within a query. Instance-set query functions
can be nested.

Example

```
CLIPS>
(deffunction count-instances (?class)
(bind ?count 0)
(do-for-all-instances ((?ins ?class)) TRUE
(bind ?count (+ ?count 1)))
?count)
CLIPS>
(deffunction count-instances-2 (?class)
(length$ (find-all-instances ((?ins ?class)) TRUE)))
CLIPS> (count-instances WOMAN)
3
CLIPS> (count-instances-2 BOY)
4
CLIPS>
```

Instance-set member variables are only in scope within the instance-set query function. Attempting
to use instance-set member variables in an outer scope will generate an error.

Example

```
CLIPS>
(deffunction last-instance (?class)
(any-instancep ((?ins ?class)) TRUE)
?ins)
```

```
[PRCCODE3] Undefined variable ?ins referenced in deffunction.
```

```
ERROR:
(deffunction MAIN::last-instance
(?class)
(any-instancep ((?ins ?class))
```

```
CLIPS Basic Programming Guide 143
```

```
TRUE)
?ins
)
CLIPS>
```

#### 9.7.6 Errors during Instance-set Query Functions

If an error occurs during an instance-set query function, the function will be immediately
terminated and the return value will be the symbol FALSE.

#### 9.7.7 Halting and Returning Values from Query Functions

The break and return functions are valid inside the action of the instance-set query functions
do-for-instance, do-for-all-instances, and delayed-do-for-all-instances. The return function is
only valid if it is applicable in the outer scope, whereas the break function actually halts the query.

#### 9.7.8 Instance-set Query Functions

The instance query system in COOL provides six functions. For a given set of instances, all six
query functions will iterate over these instances in the same order. However, if a particular instance
is deleted and recreated, the iteration order will change.

9.7.8.1 Testing if Any Instance-set Satisfies a Query

The any-instancep function applies a query to each instance-set that matches the template. If an
instance-set satisfies the query, then the function is immediately terminated, and the return value
is the symbol TRUE. Otherwise, the return value is the symbol FALSE.

Syntax

```
(any-instancep <instance-set-template> <query>)
```

Example

```
Are there any men over age 30?
```

```
CLIPS> (any-instancep ((?man MAN)) (> ?man:age 30))
TRUE
CLIPS>
```

```
144 Section 9: CLIPS Object Oriented Language
```

9.7.8.2 Determining the First Instance-set Satisfying a Query

The find-instance function applies a query to each instance-set that matches the template. If an
instance-set satisfies the query, then the function is immediately terminated, and the instance-set
is returned in a multifield value. Otherwise, the return value is a zero-length multifield value. Each
field of the multifield value is an instance-name representing an instance-set member.

Syntax

```
(find-instance <instance-set-template> <query>)
```

Example

```
Find the first pair of a man and a woman who have the same age.
```

```
CLIPS>
(find-instance ((?m MAN) (?w WOMAN)) (= ?m:age ?w:age))
([Man-1] [Woman-1])
CLIPS>
```

9.7.8.3 Determining All Instance-sets Satisfying a Query

The find-all-instances function applies a query to each instance-set that matches the template.
Each instance-set that satisfies the query is stored in a multifield value. This multifield value is
returned when the query has been applied to all possible instance-sets. If there are n instances in
each instance-set, and m instance-sets satisfied the query, then the length of the returned multifield
value will be n \* m. The first n fields correspond to the first instance-set, and so on. Each field of
the multifield value is an instance-name representing an instance-set member.

Syntax

```
(find-all-instances <instance-set-template> <query>)
```

Example

```
Find all pairs of a man and a woman who have the same age.
```

```
CLIPS>
(find-all-instances ((?m MAN) (?w WOMAN)) (= ?m:age ?w:age))
([Man-1] [Woman-1] [Man-2] [Woman-2])
CLIPS>
```

9.7.8.4 Executing an Action for the First Instance-set Satisfying a Query

The do-for-instance function applies a query to each instance-set that matches the template. If an
instance-set satisfies the query, the specified action is executed, and the function is immediately

```
CLIPS Basic Programming Guide 145
```

terminated. The return value is the evaluation of the action. If no instance-set satisfied the query,
then the return value is the symbol FALSE.

Syntax

```
(do-for-instance <instance-set-template> <query> <action>*)
```

Example

```
Print out the first triplet of different people that have the same age. The calls to neq in the
query eliminate the permutations where two or more members of the instance-set are identical.
```

```
CLIPS>
(do-for-instance ((?p1 PERSON) (?p2 PERSON) (?p3 PERSON))
(and (= ?p1:age ?p2:age ?p3:age)
(neq ?p1 ?p2)
(neq ?p1 ?p3)
(neq ?p2 ?p3))
(println ?p1 " " ?p2 " " ?p3))
[Girl-2] [Boy-2] [Boy-3]
CLIPS>
```

9.7.8.5 Executing an Action for All Instance-sets Satisfying a Query

The do-for-all-instances function applies a query to each instance-set that matches the template.
If an instance-set satisfies the query, the specified action is executed. The return value is the
evaluation of the action for the last instance-set that satisfied the query. If no instance-set satisfied
the query, then the return value is the symbol FALSE.

Syntax

```
(do-for-all-instances <instance-set-template> <query> <action>*)
```

Example

```
Print out all triplets of different people that have the same age. The calls to str-compare limit
the instance-sets that satisfy the query to combinations instead of permutations. Without these
restrictions, two instance-sets that differed only in the order of their members would both
satisfy the query.
```

```
CLIPS>
(do-for-all-instances ((?p1 PERSON) (?p2 PERSON) (?p3 PERSON))
(and (= ?p1:age ?p2:age ?p3:age)
(> (str-compare ?p1 ?p2) 0)
(> (str-compare ?p2 ?p3) 0))
(println ?p1 " " ?p2 " " ?p3))
[Girl-2] [Boy-3] [Boy-2]
[Girl-2] [Boy-4] [Boy-2]
```

```
146 Section 9: CLIPS Object Oriented Language
```

```
[Girl-2] [Boy-4] [Boy-3]
[Boy-4] [Boy-3] [Boy-2]
CLIPS>
```

9.7.8.6 Executing a Delayed Action for All Instance-sets
Satisfying a Query

The delayed-do-for-all-instances function is similar to do-for-all-instances function except that
it groups all instance-sets that satisfy the query into an intermediary multifield value. If there are
no instance-sets which satisfy the query, then the function returns the symbol FALSE. Otherwise,
the specified action is executed for each instance-set in the multifield value, and the return value
is the evaluation of the action for the last instance-set to satisfy the query. The intermediary
multifield value is discarded. This function should be used in lieu of do-for-all-instances when
the action applied to one instance-set would change the result of the query for another instance-set
(unless that is the desired effect).

Syntax

```
(delayed-do-for-all-instances <instance-set-template>
<query> <action>*)
```

Example

```
Delete all boys with the greatest age. The test in this case is another query function that
determines if there are any older boys than the one currently being examined. The action needs
to be delayed until all boys have been processed, or the greatest age will decrease as the older
boys are deleted.
```

```
CLIPS> (watch instances)
CLIPS>
(delayed-do-for-all-instances ((?b1 BOY))
(not (any-instancep ((?b2 BOY))
(> ?b2:age ?b1:age)))
(send ?b1 delete))
<== instance [Boy-1] of BOY
TRUE
CLIPS> (unwatch instances)
CLIPS> (reset)
CLIPS> (watch instances)
CLIPS>
(do-for-all-instances ((?b1 BOY))
(not (any-instancep ((?b2 BOY))
(> ?b2:age ?b1:age)))
(send ?b1 delete))
<== instance [Boy-1] of BOY
<== instance [Boy-2] of BOY
<== instance [Boy-3] of BOY
<== instance [Boy-4] of BOY
TRUE
```

CLIPS Basic Programming Guide 147

```
CLIPS> (unwatch instances)
CLIPS>
```

```
148 Section 10: Defmodule Construct
```

## Section 10: Defmodule Construct

CLIPS provides support for the modular development and execution of knowledge bases with the
defmodule construct. CLIPS modules allow a set of constructs to be grouped together such that
explicit control can be maintained over restricting the access of the constructs by other modules.
This type of control is similar to global and local scoping used in languages such as C (note,
however, that the global scoping used by CLIPS is strictly hierarchical and in one direction only—
if module A can see constructs from module B, then it is not possible for module B to see any of
module A’s constructs). Modules are also used by rules to provide execution control. See sections
12.12, 12.20, and 13.7 for additional information on functions and commands used with modules.

### 10.1 Defining Modules

Modules are defined using the defmodule construct.

Syntax

```
(defmodule <module-name> [<comment>]
<port-specification>*)
```

```
<port-specification> ::= (export <port-item>) |
(import <module-name> <port-item>)
```

```
<port-item> ::= ?ALL |
?NONE |
<port-construct> ?ALL |
<port-construct> ?NONE |
<port-construct> <construct-name>+
```

```
<port-construct> ::= deftemplate | defclass |
defglobal | deffunction |
defgeneric
```

A defmodule cannot be redefined or deleted once it is defined (with the exception of the MAIN
module which can be redefined once). The only way to delete a module is with the clear command.
Upon startup and after a clear command, CLIPS automatically constructs the following
defmodule.

```
(defmodule MAIN)
```

All of the predefined system classes belong to the MAIN module. However, it is not necessary to
import or export the system classes; they are always in scope. Otherwise, the predefined MAIN

```
CLIPS Basic Programming Guide 149
```

module does not import or export any constructs. However, unlike other modules, the MAIN
module can be redefined once after startup or a clear command.

Example

```
(defmodule CONSTANTS (export defglobal max-users))
```

```
(defmodule DATA (export deftemplate ?ALL))
```

```
(defmodule UTILITIES (export ?ALL))
```

```
(defmodule PROCESS
(import CONSTANTS defglobal ?ALL)
(import UTILITIES ?ALL)
(import DATA deftemplate ?ALL)
(export ?ALL))
```

### 10.2 Specifying a Construct’s Module...................................................................................

The module in which a construct is placed can be specified when the construct is defined. The
deffacts, deftemplate, defrule, deffunction, defgeneric, defclass, and definstances constructs all
specify the module for the construct by including it as part of the name. The module of a defglobal
construct is indicated by specifying the module name after the defglobal keyword. The module of
a defmessage-handler is specified as part of the class specifier. The module of a defmethod is
specified as part of the generic function specifier.

Example 1

```
(defmodule COMMON (export ?ALL))
```

```
(deftemplate COMMON::sensor
(slot name)
(slot value))
```

```
(deftemplate COMMON::fault
(slot name))
```

```
(defglobal COMMON ?*sensor-count* = 20)
```

```
(defclass COMMON::COMPONENT (is-a USER)
(slot flux)
(slot flow))
```

```
(defmessage-handler COMMON::COMPONENT get-charge ()
(* ?self:flux ?self:flow))
```

```
(defmethod COMMON::combine ((?x COMPONENT) (?y COMPONENT))
(+ (send ?x get-charge) (send ?y get-charge)))
```

```
(defmodule DETECT (import COMMON ?ALL))
```

```
150 Section 10: Defmodule Construct
```

```
(defrule DETECT::Find-Fault
(sensor (name ?name) (value bad))
=>
(assert (fault (name ?name))))
```

Example 2

```
CLIPS> (clear)
CLIPS> (defmodule START)
CLIPS> (defmodule END)
CLIPS> (clear)
CLIPS> (defmodule START)
CLIPS> (defmodule FINISH)
CLIPS> (defrule close =>)
CLIPS> (defrule START::open =>)
CLIPS> (list-defrules)
open
For a total of 1 defrule.
CLIPS> (set-current-module FINISH)
START
CLIPS> (list-defrules)
close
For a total of 1 defrule.
CLIPS>
```

### 10.3 Specifying Modules

Commands such as undefrule and ppdefrule require the name of a construct on which to operate.
With modules, however, it is possible to have a construct with the same name in two different
modules. The modules associated with a name can be specified either explicitly or implicitly. To
explicitly specify a name’s module the module name (a symbol) is listed followed by two colons,
::, and then the name is listed. The module name followed by :: is referred to as a module specifier.
For example, MAIN::find-stuff, refers to the find-stuff construct in the MAIN module. A module
can also be implicitly specified since there is always a current module. The current module is
changed whenever a defmodule construct is defined or the set-current-module function is used.
The MAIN module is automatically defined by CLIPS and by default is the current module when
CLIPS is started or after a clear command is issued. Thus the name find-stuff would implicitly
have the MAIN module as its module when CLIPS is first started.

```
CLIPS> (clear)
CLIPS> (defmodule MATH-CONSTANTS)
CLIPS> (defglobal MATH-CONSTANTS ?*chebyshev-constant* = 0.590170299508048)
CLIPS> (defmodule SYSTEM-CONSTANTS)
CLIPS> (defglobal SYSTEM-CONSTANTS ?*max-files* = 100)
CLIPS> (ppdefglobal max-files)
(defglobal SYSTEM-CONSTANTS ?*max-files* = 100)
CLIPS> (ppdefglobal SYSTEM-CONSTANTS::max-files)
(defglobal SYSTEM-CONSTANTS ?*max-files* = 100)
CLIPS> (ppdefglobal chebyshev-constant)
```

```
CLIPS Basic Programming Guide 151
```

```
[PRNTUTIL1] Unable to find defglobal 'chebyshev-constant'.
CLIPS> (ppdefglobal MATH-CONSTANTS::chebyshev-constant)
(defglobal MATH-CONSTANTS ?*chebyshev-constant* = 0.590170299508048)
CLIPS>
```

### 10.4 Importing and Exporting Constructs

Unless specifically exported and imported, the constructs of one module may not be used by
another module. A construct is said to be visible or within scope of a module if that construct can
be used by the module. For example, if module SCHEDULE wants to use the person deftemplate
defined in module COMMON, then module COMMON must export the person deftemplate and
module SCHEDULE must import the person deftemplate from module COMMON.

```
CLIPS> (clear)
CLIPS> (defmodule COMMON)
CLIPS>
(deftemplate COMMON::person
(slot name)
(slot position)
(multislot available))
CLIPS> (defmodule SCHEDULE)
CLIPS>
(defrule SCHEDULE::unavailable
(person (name ?name) (availbale))
=>
(println ?name " is unavailable" crlf))
```

```
[PRNTUTIL2] Syntax Error: Check appropriate syntax for defrule.
```

```
ERROR:
(defrule SCHEDULE::unavailable
(person (
CLIPS> (clear)
CLIPS> (defmodule COMMON (export deftemplate person))
CLIPS>
(deftemplate COMMON::person
(slot name)
(slot position)
(multislot available))
CLIPS> (defmodule SCHEDULE (import COMMON deftemplate person))
CLIPS>
(defrule SCHEDULE::unavailable
(person (name ?name) (available))
=>
(println ?name " is unavailable" crlf))
CLIPS>
```

CLIPS will not allow a module or other construct to be defined that causes two constructs with the
same name to be visible within the same module.

```
152 Section 10: Defmodule Construct
```

#### 10.4.1 Exporting Constructs

The export specification in a defmodule definition is used to indicate which constructs will be
accessible to other modules importing from the module being defined. Only deftemplates
(including those created for ordered facts), defclasses, defglobals, deffunctions, and defgenerics
may be exported. A module may export any valid constructs that are visible to it (not just constructs
that it defines).

There are three different types of export specifications. First, a module may export all valid
constructs that are visible to it. This accomplished by following the export keyword with the ?ALL
keyword. Second, a module may export all valid constructs of a particular type that are visible to
it. This accomplished by following the export keyword with the name of the construct type
followed by the ?ALL keyword. Third, a module may export specific constructs of a particular type
that are visible to it. This accomplished by following the export keyword with the name of the
construct type followed by the name of one or more visible constructs of the specified type. In the
following code, defmodule COMMON exports all of its constructs; defmodule DATA exports all
of its deftemplates; and defmodule CONSTANTS exports the Chebyshev, MKB, and Smarandache
defglobals.

```
(defmodule COMMON (export ?ALL))
```

```
(defmodule DATA (export deftemplate ?ALL))
```

```
(defmodule CONSTANTS (export defglobal Chebyshev MKB Smarandache))
```

The ?NONE keyword may be used in place of the ?ALL keyword to indicate either that no
constructs are exported from a module or that no constructs of a particular type are exported from
a module.

Defmethods and defmessage-handlers cannot be explicitly exported. Exporting a defgeneric
automatically exports all associated defmethods. Exporting a defclass automatically exports all
associated defmessage-handlers. Deffacts, definstances, and defrules are never exported regardless
of the export settings for a module.

#### 10.4.2 Importing Constructs

The import specification in a defmodule definition is used to indicate which constructs the module
being defined will use from other modules. Only deftemplates, defclasses, defglobals,
deffunctions, and defgenerics may be imported. Deffacts, definstances, and defrules are never
imported regardless of the import settings for a module.

There are three different types of import specifications. First, a module may import all valid
constructs that are visible to a specified module. This accomplished by following the import
keyword with a module name followed by the ?ALL keyword. Second, a module may import all

```
CLIPS Basic Programming Guide 153
```

valid constructs of a particular type that are visible to a specified module. This accomplished by
following the import keyword with a module name followed by the name of the construct type
followed by the ?ALL keyword. Third, a module may import specific constructs of a particular
type that are visible to it. This accomplished by following the import keyword with a module name
followed by the name of the construct type followed by the name of one or more visible constructs
of the specified type. In the following code, defmodule START imports all of module COMMON’s
constructs; defmodule UPDATE imports all of module DATA’s deftemplates; and defmodule
COMPUTE imports the Chebyshev, MKB, and Smarandache defglobals from module
CONSTANTS.

```
(defmodule START (import COMMON ?ALL))
```

```
(defmodule UPDATE (import DATA deftemplate ?ALL))
```

```
(defmodule COMPUTE (import CONSTANTS defglobal Chebyshev MKB Smarandache))
```

The ?NONE keyword may be used in place of the ?ALL keyword to indicate either that no
constructs are imported from a module or that no constructs of a particular type are imported from
a module.

Defmethods and defmessage-handlers cannot be explicitly imported. Importing a defgeneric
automatically imports all associated defmethods. Importing a defclass automatically imports all
associated defmessage-handlers. Deffacts, definstances, and defrules cannot be imported.

A module must be defined before it is used in an import specification. In addition, if specific
constructs are listed in the import specification, they must already be defined in the module
exporting them. It is not necessary to import a construct from the module in which it is defined in
order to use it. A construct can be indirectly imported from a module that directly imports and then
exports the module to be used.

### 10.5 Importing and Exporting Facts and Instances

Facts and instances are “owned” by the module in which their corresponding deftemplate or
defclass is defined, not by the module which creates them. Facts and instances are thus visible only
to those modules that import the corresponding deftemplate or defclass. This allows a knowledge
base to be partitioned such that rules and other constructs can only “see” those facts and instances
that are of interest to them. Instance names, however, are global in scope, so it is still possible to
send messages to an instance of a class that is not in scope.

Example

```
CLIPS> (clear)
CLIPS> (defmodule COMMON (export deftemplate player team))
CLIPS>
```

```
154 Section 10: Defmodule Construct
```

```
(deftemplate COMMON::player
(slot name)
(slot age))
CLIPS>
(deftemplate COMMON::team
(slot name)
(multislot players))
CLIPS>
(deffacts COMMON::league
(player (name Fred) (age 15))
(player (name Jill) (age 13))
(player (name Sam) (age 14))
(team (name Tigers) (players Fred Jill Sam)))
CLIPS> (defmodule ELIGIBLE (import COMMON deftemplate player))
CLIPS> (reset)
CLIPS> (facts COMMON)
f-1 (player (name Fred) (age 15))
f-2 (player (name Jill) (age 13))
f-3 (player (name Sam) (age 14))
f-4 (team (name Tigers) (players Fred Jill Sam))
For a total of 4 facts.
CLIPS> (facts ELIGIBLE)
f-1 (player (name Fred) (age 15))
f-2 (player (name Jill) (age 13))
f-3 (player (name Sam) (age 14))
For a total of 3 facts.
CLIPS>
```

#### 10.5.1 Specifying Instance-Names

Instance-names are required to be unique regardless of the module that owns them. However, the
syntax of instance-names also allows module specifications (note that the left and right brackets
in bold are to be typed and do not indicate an optional part of the syntax).

Syntax

```
<instance-name> ::= [ <symbol> ] |
[ ::<symbol> ] |
[ <module>::symbol> ]
```

Specifying just a symbol as the instance-name, such as [Rolls-Royce], will search for the instance
in all modules. Specifying only the :: before the name, such as [::Rolls-Royce], will search for the
instance first in the current module and then recursively in the imported modules as defined in the
module definition. Specifying both a symbol and a module name, such as [CARS::Rolls-Royce],
searches for the instance only in the specified module.

```
CLIPS Basic Programming Guide 155
```

### 10.6 Modules and Rule Execution

Each module has its own pattern-matching network for its rules and its own agenda. When a run
command is given, the agenda of the module that is the current focus is executed (note that the
reset and clear commands make the MAIN module the current focus). Rule execution continues
until another module becomes the current focus, no rules are left on the agenda, or the return
function is used from the RHS of a rule. Whenever the module with current focus has no remaining
activations on its agenda, the current focus is removed from the focus stack, and the next module
on the focus stack becomes the current focus. Before a rule executes, the current module is changed
to the module in which the executing rule is defined (the current focus), but otherwise the current
focus and the current module can be different. The current focus can be changed by using the focus
command (see section 13.73).

Example

```
CLIPS> (clear)
CLIPS> (defmodule MAIN (export deftemplate list))
CLIPS> (deftemplate list (slot name) (multislot numbers))
CLIPS>
(deffacts initial
(list (name A) (numbers 3 8 2 9 3 4 7))
(list (name B) (numbers 1 6 3 9 5 8 0)))
CLIPS>
(defrule start
=>
(focus SORT PRINT))
CLIPS> (defmodule SORT (import MAIN deftemplate list))
CLIPS>
(defrule sort
?f <- (list (numbers $?b ?x ?y&:(> ?x ?y) $?e))
=>
(modify ?f (numbers ?b ?y ?x ?e)))
CLIPS> (defmodule PRINT (import MAIN deftemplate list))
CLIPS>
(defrule print
(list (name ?name) (numbers $?numbers))
=>
(println "Sorted list " ?name " is " (implode$ ?numbers)))
CLIPS> (reset)
CLIPS> (run)
Sorted list A is 2 3 3 4 7 8 9
Sorted list B is 0 1 3 5 6 8 9
CLIPS>
```

```
156 Section 11: Constraint Attributes
```

## Section 11:

## Constraint Attributes

This section describes the constraint attributes that can be associated with deftemplates and
defclasses so that type checking can be performed on slot values when template facts and instances
are created. The constraint information is also analyzed for the patterns on the LHS of a rule to
determine if the specified constraints prevent the rule from being satisfied.

Two types of constraint checking are supported: static and dynamic. Static constraint checking is
always enabled and checks constraint violations when function calls and constructs are parsed.
This includes constraint checking between patterns on the LHS of a rule when variables are used
in more than one slot. When dynamic constraint checking is enabled, newly created data objects
(such as deftemplate facts and instances) have their slot values checked for constraint violations.
Essentially, static constraint checking occurs when a CLIPS program is loaded and dynamic
constraint checking occurs when a CLIPS program is running. By default, dynamic constraint
checking is disabled. It can be enabled using the set-dynamic-constraint-checking function.

Unless dynamic constraint checking is enabled, constraint information associated with constructs
is not saved when a binary image is created using the bsave command.

The general syntax for constraint attributes is shown following.

Syntax

```
<constraint-attribute> ::= <type-attribute> |
<allowed-constant-attribute> |
<range-attribute> |
<cardinality-attribute>
```

### 11.1 Type Attribute

The type attribute allows the types of values to be stored in a slot to be restricted.

Syntax

```
<type-attribute> ::= (type <type-specification>)
```

```
<type-specification> ::= <allowed-type>+ | ?VARIABLE
```

```
<allowed-type>
::= SYMBOL | STRING | LEXEME |
INTEGER | FLOAT | NUMBER |
INSTANCE-NAME | INSTANCE-ADDRESS | INSTANCE |
```

```
CLIPS Basic Programming Guide 157
```

```
EXTERNAL-ADDRESS | FACT-ADDRESS
```

Using NUMBER for this attribute is equivalent to using both INTEGER and FLOAT. Using
LEXEME for this attribute is equivalent to using both SYMBOL and STRING. Using INSTANCE
for this attribute is equivalent to using both INSTANCE-NAME and INSTANCE-ADDRESS. The
keyword ?VARIABLE allows any type to be stored.

### 11.2 Allowed Constant Attributes..........................................................................................

The allowed constant attributes restrict the constant values of a specific type that can be stored in
a slot. The list of values provided should either be a list of constants of the specified type or the
keyword ?VARIABLE which means any constant of that type is allowed. The allowed-values
attribute allows the slot to be restricted to a specific set of values (encompassing all types). Note
the difference between using the attribute (allowed-symbols red green blue) and (allowed-values
red green blue). The allowed-symbols attribute states that if the value is of type symbol, then its
value must be one of the listed symbols. The allowed-values attribute completely restricts the
allowed values to the listed values. The allowed-classes attribute does not restrict the slot value in
the same manner as the other allowed constant attributes. Instead, if this attribute is specified and
the slot value is either an instance address or instance name, then the class to which the instance
belongs must be a class specified in the allowed-classes attribute or be a subclass of one of the
specified classes.

Syntax

```
<allowed-constant-attribute>
::= (allowed-symbols <symbol-list>) |
(allowed-strings <string-list>) |
(allowed-lexemes <lexeme-list> |
(allowed-integers <integer-list>) |
(allowed-floats <float-list>) |
(allowed-numbers <number-list>) |
(allowed-instance-names <instance-list>) |
(allowed-classes <class-name-list>)
(allowed-values <value-list>)
```

```
<symbol-list> ::= <symbol>+ | ?VARIABLE
```

```
<string-list> ::= <string>+ | ?VARIABLE
```

```
<lexeme-list> ::= <lexeme>+ | ?VARIABLE
```

```
<integer-list> ::= <integer>+ | ?VARIABLE
```

```
<float-list> ::= <float>+ | ?VARIABLE
```

```
<number-list> ::= <number>+ | ?VARIABLE
```

```
<instance-name-list> ::= <instance-name>+ | ?VARIABLE
```

```
158 Section 11: Constraint Attributes
```

```
<class-name-list> ::= <class-name>+ | ?VARIABLE
```

```
<value-list> ::= <constant>+ | ?VARIABLE
```

Specifying the allowed-lexemes attribute is equivalent to specifying constant restrictions on both
symbols and strings. A string or symbol must match one of the constants in the attribute list. Type
conversion from symbols to strings and strings to symbols is not performed. Similarly, specifying
the allowed-numbers attribute is equivalent to specifying constant restrictions on both integers and
floats.

### 11.3 Range Attribute

The range attribute allows a numeric range to be specified for a slot when a numeric value is used
in that slot. If a numeric value is not used in that slot, then no checking is performed.

Syntax

```
<range-attribute> ::= (range <range-specification>
<range-specification>)
```

```
<range-specification> ::= <number> | ?VARIABLE
```

Either integers or floats can be used in the range specification. The first value to the range attribute
signifies the minimum allowed value and the second value signifies the maximum value. Integers
will be temporarily converted to floats when necessary to perform range comparisons. If the
keyword ?VARIABLE is used for the minimum value, then the minimum value is negative infinity
(-∞). If the keyword ?VARIABLE is used for the maximum value, then the maximum value is
positive infinity (+∞). The range attribute cannot be used in conjunction with the allowed-values,
allowed-numbers, allowed-integers, or allowed-floats attributes.

### 11.4 Cardinality Attribute

The cardinality attribute restricts the number of fields that can be stored in a multifield slot. This
attribute can not be used with a single field slot.

Syntax

```
<cardinality-attribute>
::= (cardinality <cardinality-specification>
<cardinality-specification>)
```

```
<cardinality-specification> ::= <integer> | ?VARIABLE
```

Only integers can be used in the cardinality specification. The first value to the cardinality attribute
signifies the minimum number of fields that can be stored in the slot and the second value signifies

```
CLIPS Basic Programming Guide 159
```

the maximum number of fields which can be stored in the slot. If the keyword ?VARIABLE is
used for the minimum value, then the minimum cardinality is zero. If the keyword ?VARIABLE
is used for the maximum value, then the maximum cardinality is positive infinity (+∞). If the
cardinality is not specified for a multifield slot, then it is assumed to be zero to infinity.

### 11.5 Deriving a Default Value From Constraints

Default values for deftemplate and instance slots are automatically derived from the constraints
for the slots if an explicit default value is not specified. The following rules are used (in order) to
determine the default value for a slot with an unspecified default value.

```
1) The default type for the slot is chosen from the list of allowed types for the slot in the
following order of precedence: SYMBOL, STRING, INTEGER, FLOAT,
INSTANCE-NAME, INSTANCE-ADDRESS, FACT-ADDRESS,
EXTERNAL-ADDRESS.
```

```
2) If the default type has an allowed constant restriction specified (such as the allowed-integers
attribute for the INTEGER type), then the first value specified in the allowed constant attribute
is chosen as the default value.
```

```
3) If the default value was not specified by step 2 and the default type is INTEGER or FLOAT
and the range attribute is specified, then the minimum range value is used as the default value
if it is not ?VARIABLE, otherwise, the maximum range value is used if it is not ?VARIABLE.
```

```
4) If the default value was not specified by step 2 or 3, then the default default value is used.
This value is nil for type SYMBOL, "" for type STRING, 0 for type INTEGER, 0.0 for type
FLOAT, [nil] for type INSTANCE-NAME, a pointer to a dummy instance for type
INSTANCE-ADDRESS, a pointer to a dummy fact for type FACT-ADDRESS, and the
NULL pointer for type EXTERNAL-ADDRESS.
```

```
5) If the default value is being derived for a single field slot, then the default value derived from
steps 1 through 4 is used. The default value for a multifield slot is a multifield value of length
zero. However, if the multifield slot has a minimum cardinality greater than zero, then a
multifield value with a length of the minimum cardinality is created and the default value that
would be used for a single field slot is stored in each field of the multifield value.
```

### 11.6 Constraint Violation Examples

The following examples illustrate some of the types of constraint violations that CLIPS can detect.

```
160 Section 11: Constraint Attributes
```

Example 1

```
The first occurrence of the variable ?v in the name slot of the first pattern of the same-values
rule restricts its allowed types to either a symbol or string. The second occurrence of ?v in the
SSN slot of the second pattern further restricts its allowed types to only symbols. The final
occurence of ?v in the third pattern generates an error because the income slot expects ?x to
be either an integer or a float, but its only allowed type is a symbol.
```

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name (type SYMBOL STRING))
(slot SSN (type SYMBOL INTEGER))
(slot income (type INTEGER FLOAT)))
CLIPS>
(defrule same-values
(person (name ?v))
(person (SSN ?v))
(person (income ?v))
=>)
```

```
[RULECSTR1] Variable ?v in CE #3 slot 'income' has constraint conflicts which
make the pattern unmatchable.
```

```
ERROR:
(defrule MAIN::same-values
(person (name ?v))
(person (SSN ?v))
(person (income ?v))
=>)
CLIPS>
```

Example 2

```
The variable ?p1, found in the coordinates slot of first pattern of the polygon-points rule,
must have two fields. The variable ?p2, found in the coordinates slot of the second pattern,
must also have two fields. Added together, both variables have four fields. Since the
coordinates slot in the the third pattern has a minimum cardinality of six, the variables ?p1
and ?p2 cannot satisfy the minimum cardinality restriction for this slot.
```

```
CLIPS> (clear)
CLIPS>
(deftemplate point
(slot id (type SYMBOL))
(multislot coordinates
(type INTEGER)
(cardinality 2 2)))
CLIPS>
(deftemplate polygon
(slot id (type SYMBOL))
(multislot coordinates
```

```
CLIPS Basic Programming Guide 161
```

```
(type INTEGER)
(cardinality 6 ?VARIABLE)))
CLIPS>
(defrule polygon-points
(point (id ?id) (coordinates $?p1))
(point (id ~?id) (coordinates $?p2))
(polygon (coordinates $?p1 $?p2))
=>)
```

```
[CSTRNCHK1] The group of restrictions found in CE #3 does not satisfy the
cardinality restrictions for slot 'coordinates'.
```

```
ERROR:
(defrule MAIN::polygon-points
(point (id ?id) (coordinates $?p1))
(point (id ~?id) (coordinates $?p2))
(polygon (coordinates $?p1 $?p2))
=>)
CLIPS>
```

Example 3

```
The variable ?month, found in the month slot of the first pattern of the date-in-january rule,
must be a symbol. Since the = function expects numeric values for its arguments, an error
occurs.
```

```
CLIPS> (clear)
CLIPS>
(deftemplate date
(slot year (type INTEGER))
(slot month (type SYMBOL))
(slot day (type INTEGER)))
CLIPS>
(defrule date-in-january
(date (month ?month))
(test (= ?month 1))
=>)
```

```
[RULECSTR2] Previous variable bindings of ?month caused the type restrictions
for argument #1 of the expression (= ?month 1)
found in CE #2 to be violated.
```

```
ERROR:
(defrule MAIN::date-in-january
(date (month ?month))
(test (= ?month 1))
=>)
CLIPS>
```

```
162 Section 11: Constraint Attributes
```

Example 4

```
The first occurrence of the variable ?age in the age slot of the first pattern of the old-and-
young rule restricts its vale to an integer in the range 13 to 19. The second occurrence of ?age
in the age slot of the second pattern further restricts its values to an integer greater than or
equal to 59. Since no integer can satisfy both of these restrictions, an error occurs.
```

```
CLIPS> (clear)
CLIPS>
(deftemplate teenager
(slot name)
(slot age (type INTEGER) (range 13 19)))
CLIPS>
(deftemplate senior
(slot name)
(slot age (type INTEGER) (range 65 ?VARIABLE)))
CLIPS>
(defrule old-and-young
(teenager (name ?name1) (age ?age))
(senior (name ?name2) (age ?age))
=>
(println ?name1 " and " ?name2 " are the same age"))
```

```
[RULECSTR1] Variable ?age in CE #2 slot 'age' has constraint conflicts which make
the pattern unmatchable.
```

```
ERROR:
(defrule MAIN::old-and-young
(teenager (name ?name1) (age ?age))
(senior (name ?name2) (age ?age))
=>
(println ?name1 " and " ?name2 " are the same age"))
CLIPS>
```

```
CLIPS Basic Programming Guide 163
```

## Section 12: Actions And Functions

This section describes various actions and functions which may be used on the LHS and RHS of
rules, from the REPL, and from other constructs such as deffunctions, defmessage-handlers, and
defmethods. The terms functions, actions, and commands should be thought of interchangeably.
However, when the term function is used it generally refers to a function that returns a value. The
term action refers to a function having no return value but performing some basic operation as a
side effect (such as printout). The term command refers to functions normally entered at the
top-level command prompt (such as the reset command, which does not return a value, and the
set-strategy command, which does return a value).

### 12.1 Predicate Functions

The following functions perform predicate tests.

#### 12.1.1 Testing For Numbers

The numberp function returns the symbol TRUE if its argument is a float or integer; otherwise,
it returns the symbol FALSE.

Syntax

```
(numberp <expression>)
```

Example

```
CLIPS> (clear)
CLIPS>
(defrule invalid-response
(response ?v)
(test (not (numberp ?v)))
=>
(println "Response " ?v " is not a number"))
CLIPS> (assert (response 3))
<Fact-1>
CLIPS> (assert (response 7.5))
<Fact-2>
CLIPS> (assert (response abc))
<Fact-3>
CLIPS> (run)
Response abc is not a number
CLIPS>
```

```
164 Section 12: Actions and Functions
```

#### 12.1.2 Testing For Floats

The floatp function returns the symbol TRUE if its argument is a float; otherwise, it returns the
symbol FALSE.

Syntax

```
(floatp <expression>)
```

#### 12.1.3 Testing For Integers

The integerp function returns the symbol TRUE if its argument is an integer; otherwise, it returns
the symbol FALSE.

Syntax

```
(integerp <expression>)
```

#### 12.1.4 Testing For Strings Or Symbols

The lexemep function returns the symbol TRUE if its argument is a string or symbol; otherwise.
it returns the symbol FALSE.

Syntax

```
(lexemep <expression>)
```

#### 12.1.5 Testing For Strings

The stringp function returns the symbol TRUE if its argument is a string; otherwise, it returns the
symbol FALSE.

Syntax

```
(stringp <expression>)
```

#### 12.1.6 Testing For Symbols

The symbolp function returns the symbol TRUE if its argument is a symbol; otherwise, it returns
the symbol FALSE.

Syntax

```
(symbolp <expression>)
```

```
CLIPS Basic Programming Guide 165
```

#### 12.1.7 Testing For Even Numbers

The evenp function returns the symbol TRUE if its argument is an even number; otherwise, it
returns the symbol FALSE.

Syntax

```
(evenp <integer-expression>)
```

#### 12.1.8 Testing For Odd Numbers

The oddp function returns the symbol TRUE if its argument is an odd number; otherwise, it
returns the symbol FALSE.

Syntax

```
(oddp <integer-expression>)
```

#### 12.1.9 Testing For Multifield Values

The multifieldp function returns the symbol TRUE if its argument is a multifield value; otherwise,
it returns the symbol FALSE.

Syntax

```
(multifieldp <expression>)
```

Example

```
CLIPS> (multifieldp (create$ red green blue))
TRUE
CLIPS> (multifieldp 3)
FALSE
CLIPS>
```

#### 12.1.10 Testing For External-Addresses

The external-addressp function returns the symbol TRUE if its argument is an external-address;
otherwise, it returns the symbol FALSE.

Syntax

```
(pointerp <expression>)
```

```
166 Section 12: Actions and Functions
```

#### 12.1.11 Comparing for Equality

The eq function returns the symbol TRUE if its first argument is equal in value to all its subsequent
arguments; otherwise, it returns the symbol FALSE. Note that eq compares types as well as values.
Thus, (eq 3 3.0) returns the symbol FALSE since 3 is an integer and 3.0 is a float.

Syntax

```
(eq <expression> <expression>+)
```

Example

```
CLIPS> (eq red green blue red)
FALSE
CLIPS> (eq red red red red)
TRUE
CLIPS> (eq 3 4)
FALSE
CLIPS>
```

#### 12.1.12 Comparing for Inequality

The neq function returns the symbol TRUE if its first argument is not equal in value to all its
subsequent arguments; otherwise, it returns the symbol FALSE. Note that neq compares types as
well as values. Thus, (neq 3 3.0) return the symbol TRUE since 3 is an integer and 3.0 is a float.

Syntax

```
(neq <expression> <expression>+)
```

Example

```
CLIPS> (neq red green blue green)
TRUE
CLIPS> (neq red red green blue)
FALSE
CLIPS> (neq 3 red)
TRUE
CLIPS>
```

#### 12.1.13 Comparing Numbers for Equality

The = function returns the symbol TRUE if its first argument is equal in value to all its subsequent
arguments; otherwise it returns the symbol FALSE. Note that = compares only numeric values
and will convert integers to floats when necessary for comparison.

```
CLIPS Basic Programming Guide 167
```

Syntax

```
(= <numeric-expression> <numeric-expression>+)
```

Example

```
CLIPS> (= 3 3.0)
TRUE
CLIPS> (= 4 4.1)
FALSE
CLIPS>
```

❖ Portability Note

Because the precision of floating point numbers varies from one computer to another, it is possible
for the numeric comparison functions to work correctly on one computer and incorrectly on
another. In fact, you should be aware, even if code is not being ported, that roundoff error can
cause erroneous results. For example, the following expression erroneously returns the symbol
TRUE because both numbers are rounded up to 0.6666666666666666667.

```
CLIPS> (= 0.66666666666666666666 0.66666666666666666667)
TRUE
CLIPS>
```

#### 12.1.14 Comparing Numbers for Inequality

The <> function returns the symbol TRUE if its first argument is not equal in value to all its
subsequent arguments; otherwise, it returns the symbol FALSE. Note that <> compares only
numeric values and will convert integers to floats when necessary for comparison.

Syntax

```
(<> <numeric-expression> <numeric-expression>+)
```

Example

```
CLIPS> (<> 3 3.0)
FALSE
CLIPS> (<> 4 4.1)
TRUE
CLIPS>
```

❖ Portability Note

See portability note in section 12.1.13.

```
168 Section 12: Actions and Functions
```

#### 12.1.15 Greater Than Comparison

The > function returns the symbol TRUE if for all its arguments, argument n-1 is greater than
argument n; otherwise, it returns the symbol FALSE. Note that > compares only numeric values
and will convert integers to floats when necessary for comparison.

Syntax

```
(> <numeric-expression> <numeric-expression>+)
```

Example

```
CLIPS> (> 5 4 3)
TRUE
CLIPS> (> 5 3 4)
FALSE
CLIPS>
```

❖ Portability Note

See portability note in section 12.1.13.

#### 12.1.16 Greater Than or Equal Comparison

The >= function returns the symbol TRUE if for all its arguments, argument n-1 is greater than or
equal to argument n; otherwise, it returns the symbol FALSE. Note that >= compares only numeric
values and will convert integers to floats when necessary for comparison.

Syntax

```
(>= <numeric-expression> <numeric-expression>+)
```

Example

```
CLIPS> (>= 5 5 3)
TRUE
CLIPS> (>= 5 3 5)
FALSE
CLIPS>
```

❖ Portability Note

See portability note in section 12.1.13.

```
CLIPS Basic Programming Guide 169
```

#### 12.1.17 Less Than Comparison

The < function returns the symbol TRUE if for all its arguments, argument n-1 is less than
argument n; otherwise it returns the symbol FALSE. Note that < compares only numeric values
and will convert integers to floats when necessary for comparison.

Syntax

```
(< <numeric-expression> <numeric-expression>+)
```

Example

```
CLIPS> (< 3 4 5)
TRUE
CLIPS> (< 3 5 4)
FALSE
CLIPS>
```

❖ Portability Note

See portability note in section 12.1.13.

#### 12.1.18 Less Than or Equal Comparison

The <= function returns the symbol TRUE if for all its arguments, argument n-1 is less than or
equal to argument n; otherwise, it returns the symbol FALSE. Note that <= compares only numeric
values and will convert integers to floats when necessary for comparison.

Syntax

```
(<= <numeric-expression> <numeric-expression>+)
```

Example

```
CLIPS> (<= 3 5 5)
TRUE
CLIPS> (<= 5 3 5)
FALSE
CLIPS>
```

❖ Portability Note

See portability note in section 12.1.13.

```
170 Section 12: Actions and Functions
```

#### 12.1.19 Boolean And

The and function returns the symbol TRUE if each of its arguments evaluates to the symbol
TRUE; otherwise, it returns the symbol FALSE. Each argument of the function is evaluated from
left to right. If any argument evaluates to the symbol FALSE, then the symbol FALSE is
immediately returned by the function.

Syntax

```
(and <expression>+)
```

#### 12.1.20 Boolean Or

The or function returns the symbol TRUE if any of its arguments evaluates to the symbol TRUE;
otherwise, it returns the symbol FALSE. Each argument of the function is evaluated from left to
right. If any argument evaluates to the symbol TRUE, then the symbol TRUE is immediately
returned by the function.

Syntax

```
(or <expression>+)
```

#### 12.1.21 Boolean Not

The not function returns the symbol TRUE if its argument evaluates to the symbol FALSE;
otherwise it returns the symbol FALSE.

Syntax

```
(not <expression>)
```

### 12.2 Multifield Functions.......................................................................................................

The following functions operate on multifield values.

#### 12.2.1 Creating Multifield Values

The create$ function appends any number of fields together to create a multifield value.

Syntax

```
(create$ <expression>*)
```

```
CLIPS Basic Programming Guide 171
```

The return value of create$ is a multifield value regardless of the number or types of arguments
(single-field or multifield). Calling create$ with no arguments creates a multifield value of length
zero.

Example

```
CLIPS (create$ hammer drill saw screw pliers wrench)
(hammer drill saw screw pliers wrench)
CLIPS> (create$ (+ 3 4) (* 2 3) (/ 8 4))
(7 6 2.0)
CLIPS> (create$)
()
CLIPS>
```

#### 12.2.2 Specifying an Element

The nth$ function will return a specified field from a multifield value.

Syntax

```
(nth$ <integer-expression> <multifield-expression>)
```

The first argument should be an integer from 1 to the number of elements within the second
argument. The symbol nil will be returned if the first argument is greater than the number of fields
in the second argument.

Example

```
CLIPS> (nth$ 3 (create$ a b c d e f g))
c
CLIPS> (nth$ 12 (create$ a b c d e f g))
nil
CLIPS>
```

#### 12.2.3 Finding an Element

The member$ function determines whether a primitive value is contained in a multifield value.

Syntax

```
(member$ <expression> <multifield-expression>)
```

If the first argument is a single field value and is one of the fields within the second argument,
member$ will return the integer position of the field (from 1 to the length of the second argument).
If the first argument is a multifield value and this value is embedded in the second argument, then
the return value is a two field multifield value consisting of the starting and ending integer indices

```
172 Section 12: Actions and Functions
```

of the first argument within the second argument. If neither of these situations is satisfied, then the
symbol FALSE is returned.

Example

```
CLIPS> (member$ blue (create$ red 3 "text" 8.7 blue))
5
CLIPS> (member$ 4 (create$ red 3 "text" 8.7 blue))
FALSE
CLIPS> (member$ (create$ b c) (create$ a b c d))
(2 3)
CLIPS>
```

#### 12.2.4 Comparing Multifield Values

The subsetp function checks if one multifield value is a subset of another (i.e., if all the fields in
the first multifield value are also in the second multifield value).

Syntax

```
(subsetp <multifield-expression> <multifield-expression>)
```

If the first argument is a subset of the second argument, this function returns the symbol TRUE;
otherwise, it returns the symbol FALSE. The order of the fields is not considered. If the first
argument is bound to a multifield of length zero, subsetp always returns the symbol TRUE.

Example

```
CLIPS> (subsetp (create$ hammer saw drill)
(create$ hammer drill wrench pliers saw))
TRUE
CLIPS> (subsetp (create$ wrench crowbar)
(create$ hammer drill wrench pliers saw))
FALSE
CLIPS> (subsetp (create$)
(create$ hammer drill wrench pliers saw))
TRUE
CLIPS> (subsetp (create$ wrench crowbar)
(create$))
FALSE
CLIPS>
```

#### 12.2.5 Deletion of Fields in Multifield Values

The delete$ function deletes the specified range from a multifield value.

```
CLIPS Basic Programming Guide 173
```

Syntax

```
(delete$ <multifield-expression>
<begin-integer-expression>
<end-integer-expression>)
```

The modified multifield value is returned, which is the same as <multifield-expression> with the
fields ranging from <begin-integer-expression> to <end-integer-expression> removed. To delete
a single field, the begin range field should equal the end range field.

Example

```
CLIPS> (delete$ (create$ hammer drill saw pliers wrench) 3 4)
(hammer drill wrench)
CLIPS> (delete$ (create$ computer printer hard-disk) 1 1)
(printer hard-disk)
CLIPS>
```

#### 12.2.6 Creating Multifield Values from Strings.

The explode$ function constructs a multifield value from a string by using each field in a string
as a field in a new multifield value.

Syntax

```
(explode$ <string-expression>)
```

A new multifield value is created in which each delimited field in order in <string-expression> is
taken to be a field in the new multifield value that is returned. A string with no fields creates a
multifield value of length zero. Fields other than symbols, strings, integer, floats, or instances
names (such as parentheses or variables) are converted to symbols.

Example

```
CLIPS> (explode$ "hammer drill saw screw")
(hammer drill saw screw)
CLIPS> (explode$ "1 2 abc 3 4 \"abc\" \"def\"")
(1 2 abc 3 4 "abc" "def")
CLIPS> (explode$ "?x ~ )")
(?x ~ ))
CLIPS>
```

#### 12.2.7 Creating Strings from Multifield Values

The implode$ function creates a single string from a multifield value.

```
174 Section 12: Actions and Functions
```

Syntax

```
(implode$ <multifield-expression>)
```

Each field in <multifield-expression> in order is concatenated into a string value with a single
blank separating fields. The new string is returned.

Example

```
CLIPS> (implode$ (create$ hammer drill screwdriver))
"hammer drill screwdriver"
CLIPS> (implode$ (create$ 1 "abc" def "ghi" 2))
"1 "abc" def "ghi" 2"
CLIPS> (implode$ (create$ "abc def ghi"))
""abc def ghi""
CLIPS>
```

#### 12.2.8 Extracting a Sub-sequence from a Multifield Value.............................................

The subseq$ function extracts a specified range from a multifield value and returns a new mul-
tifield value containing just the sub-sequence.

Syntax

```
(subseq$ <multifield-value>
<begin-integer-expression>
<end-integer-expression>)
```

The second and third arguments to the function are integers specifying the begin and end fields of
the desired sub-sequence in <multifield-expression>.

Example

```
CLIPS> (subseq$ (create$ hammer drill wrench pliers) 3 4)
(wrench pliers)
CLIPS> (subseq$ (create$ 1 "abc" def "ghi" 2) 1 1)
(1)
CLIPS>
```

#### 12.2.9 Replacing Fields within a Multifield Value

The replace$ function replaces a range of field in a multifield value with a series of single-field
and/or multifield values and returns a new multifield value containing the replacement values
within the original multifield value.

```
CLIPS Basic Programming Guide 175
```

Syntax

```
(replace$ <multifield-expression>
<begin-integer-expression>
<end-integer-expression>
<single-or-multi-field-expression>+)
```

The <begin-integer-expression> to <end-integer-expression> argurments is the range of values to
be replaced.

Example

```
CLIPS> (replace$ (create$ drill wrench pliers) 3 3 machete)
(drill wrench machete)
CLIPS> (replace$ (create$ a b c d) 2 3 x y (create$ q r s))
(a x y q r s d)
CLIPS>
```

#### 12.2.10 Inserting Fields within a Multifield Value

The insert$ function inserts a series of single-field and/or multifield values at a specified location
in a multifield value with and returns a new multifield value containing the inserted values within
the original multifield value.

Syntax

```
(insert$ <multifield-expression>
<integer-expression>
<single-or-multi-field-expression>+)
```

The <integer-expression> argument is the location where the values are to be inserted. This value
must be greater than or equal to 1. A value of 1 inserts the new value(s) at the beginning of the
<multifield-expression>. Any value greater than the length of the <multifield-expression> appends
the new values to the end of the <multifield-expression>.

Example

```
CLIPS> (insert$ (create$ a b c d) 1 x)
(x a b c d)
CLIPS> (insert$ (create$ a b c d) 4 y z)
(a b c y z d)
CLIPS> (insert$ (create$ a b c d) 5 (create$ q r))
(a b c d q r)
CLIPS>
```

```
176 Section 12: Actions and Functions
```

#### 12.2.11 Getting the First Field from a Multifield Value

The first$ function returns the first field of a multifield value as a multifield value

Syntax

```
(first$ <multifield-expression>)
```

Example

```
CLIPS> (first$ (create$ a b c))
(a)
CLIPS> (first$ (create$))
()
CLIPS>
```

12.2.12 Getting All but the First Field from a Multifield Value

The rest$ function returns all but the first field of a multifield value as a multifield value.

Syntax

```
(rest$ <multifield-expression>)
```

Example

```
CLIPS> (rest$ (create$ a b c))
(b c)
CLIPS> (rest$ (create$))
()
CLIPS>
```

### 12.2.13 Determining the Number of Fields in a Multifield Value...................................

The length$ function returns an integer indicating the number of fields contained in a multifield
value.

Syntax

```
(length$ <multifield-expression>)
```

Example

```
CLIPS> (length$ (create$ a b c d e f g))
7
CLIPS>
```

```
CLIPS Basic Programming Guide 177
```

### 12.2.14 Deleting Specific Values within a Multifield Value

The delete-member$ function deletes specific values contained within a multifield value and
returns the modified multifield value.

Syntax

```
(delete-member$ <multifield-expression> <expression>+)
```

The <expression>+ term is one or more values to be deleted from <multifield-expression>. If
<expression> is a multifield value, the entire sequence must be contained within the first argument
in the correct order.

Example

```
CLIPS> (delete-member$ (create$ a b a c) b a)
(c)
CLIPS> (delete-member$ (create$ a b c c b a) (create$ b a))
(a b c c)
CLIPS>
```

### 12.2.15 Replacing Specific Values within a Multifield Value

The replace-member$ function replaces specific values contained within a multifield value and
returns the modified multifield value.

Syntax

```
(replace-member$ <multifield-expression> <substitute-expression>
<search-expression>+)
```

Any <search-expression> value that is contained within <multifield-expression> is replaced by
<substitute-expression>.

Example

```
CLIPS> (replace-member$ (create$ a b a b) (create$ a b a) a b)
(a b a a b a a b a a b a)
CLIPS> (replace-member$ (create$ a b a b) (create$ a b a) (create$ a b))
(a b a a b a)
CLIPS>
```

### 12.2.16 Creating the Union of Multifield Values

The union$ function creates a multifield value containing a single occurrence of each value
contained within each of its multifield arguments.

```
178 Section 12: Actions and Functions
```

Syntax

```
(union$ <multifield-expression>*)
```

Example

```
CLIPS> (union$ (create$ a b b c) (create$ d e e f))
(a b c d e f)
CLIPS> (union$)
()
CLIPS>
```

### 12.2.17 Creating the Intersection of Multifield Values

The intersection$ function creates a multifield value containing a single occurrence of each value
that is contained within all of its multifield arguments.

Syntax

```
(intersection$ <multifield-expression>*)
```

Example

```
CLIPS> (intersection$ (create$ a b b c) (create$ b c c e))
(b c)
CLIPS> (intersection$ (create$ a b c) (create$ d e f))
()
CLIPS>
```

### 12.2.18 Creating the Difference of Multifield Values

The difference$ function creates a multifield value containing a single occurrence of each value
that is contained within its first argument, but none of its subsequent multifield arguments.

Syntax

```
(difference$ <multifield-expression>+)
```

Example

```
CLIPS> (difference$ (create$ a b b c d) (create$ a c))
(b d)
CLIPS> (difference$ (create$ a b b c))
(a b c)
CLIPS>
```

```
CLIPS Basic Programming Guide 179
```

## 12.3 String Functions

The following functions perform operations that are related to strings.

### 12.3.1 String Concatenation

The str-cat function will concatenates its arguments into a single string.

Syntax

```
(str-cat <expression>*)
```

Each <expression> should be one of the following types: symbol, string, float, integer, or
instance-name.

Example

```
CLIPS> (str-cat 2018 "-" 5 "-" 29)
"2018- 5 - 29"
CLIPS>
```

### 12.3.2 Symbol Concatenation

The sym-cat function will concatenate its arguments into a single symbol. It is functionally
identical to the str-cat function with the exception that the returned value is a symbol and not a
string.

Syntax

```
(sym-cat <expression>*)
```

Each <expression> should be one of the following types: symbol, string, float, integer, or
instance-name.

### 12.3.3 Taking a String Apart............................................................................................

The sub-string function will retrieve a portion of a string from another string.

Syntax

```
(sub-string <integer-expression> <integer-expression>
<string-expression>)
```

```
180 Section 12: Actions and Functions
```

The first argument, counting from one, must be a number marking the beginning position in the
string and the second argument must be a number marking the ending position in the string. If the
first argument is greater than the second argument, the string "" is returned.

Example

```
CLIPS> (sub-string 3 8 "abcdefghijkl")
"cdefgh"
CLIPS>
```

### 12.3.4 Searching a String

The str-index function will return the position of a string inside another string.

Syntax

```
(str-index <lexeme-expression> <lexeme-expression>)
```

The second argument is searched for the first occurrence of the first argument. The str-index
function returns the integer starting position, counting from one, of the first argument in the second
argument; otherwise if the first argument is not contained in the second argument, the symbol
FALSE is returned.

Example

```
CLIPS> (str-index "def" "abcdefghi")
4
CLIPS> (str-index "qwerty" "qwertypoiuyt")
1
CLIPS> (str-index "qwerty" "poiuytqwer")
FALSE
```

### CLIPS>

### 12.3.5 Evaluating a Function within a String

The eval function evaluates the string as though it were entered at the Read-Eval-Print Loop
(REPL).

Syntax

```
(eval <string-or-symbol-expression>)
```

The only argument is a string containing the command, constant, or local/global variable to be
evaluated. NOTE: eval will not evaluate any of the construct definition forms (i.e., defrule,
deffacts, etc.). The return value is the result of the evaluation of the string if no errors occur;
otherwise, the symbol FALSE is returned.

```
CLIPS Basic Programming Guide 181
```

Example

```
CLIPS> (bind ?y 3)
3
CLIPS> (defglobal ?*x* = 4)
CLIPS> (eval "(+ 3 4)")
7
CLIPS> (eval "(+ ?*x* ?y)")
7
CLIPS> (eval "?*x*")
4
CLIPS> (eval "?y")
3
CLIPS> (eval "3")
3
CLIPS>
```

### 12.3.6 Evaluating a Construct within a String

The build function evaluates the string as though it were entered at the REPL.

Syntax

```
(build <string-or-symbol-expression>)
```

The only argument is the construct to be added. The return value is the symbol TRUE if the
construct was successfully added; otherwise the symbol FALSE is returned.

The build function is not available for binary-load only or run-time CLIPS configurations (see the
Advanced Programming Guide).

Example

```
CLIPS> (clear)
CLIPS> (build "(defrule hello => (println \"Hello\"))")
TRUE
CLIPS> (rules)
hello
For a total of 1 defrule.
CLIPS> (run)
Hello
CLIPS>
```

### 12.3.7 Converting a String to Uppercase

The upcase function will return a string or symbol with uppercase alphabetic characters.

```
182 Section 12: Actions and Functions
```

Syntax

```
(upcase <string-or-symbol-expression>)
```

Example

```
CLIPS> (upcase "This is a test of upcase")
"THIS IS A TEST OF UPCASE"
CLIPS> (upcase A_Word_Test_for_Upcase)
A_WORD_TEST_FOR_UPCASE
CLIPS>
```

### 12.3.8 Converting a String to Lowercase.........................................................................

The lowcase function will return a string or symbol with lowercase alphabetic characters.

Syntax

```
(lowcase <string-or-symbol-expression>)
```

Example

```
CLIPS> (lowcase "This is a test of lowcase")
"this is a test of lowcase"
CLIPS> (lowcase A_Word_Test_for_Lowcase)
a_word_test_for_lowcase
CLIPS>
```

### 12.3.9 Comparing Two Strings

The str-compare function will compare two strings lexicographically to determine their logical
relationship (i.e., equal to, less than, greater than). The comparison is performed
character-by-character until the strings are exhausted (implying equal strings) or unequal
characters are found. The positions of the unequal characters within the ASCII character set are
used to determine the logical relationship of unequal strings.

Syntax

```
(str-compare <string-or-symbol-expression>
<string-or-symbol-expression>)
```

This function returns an integer representing the result of the comparison (0 if the strings are equal,

- 1 if the first argument is less than the second argument, and 1 if the first argument is greater than
  the second argument).

```
CLIPS Basic Programming Guide 183
```

Example

```
CLIPS> (str-compare "string" "string")
0
CLIPS> (str-compare "string1" "string2")
```

- 1
  CLIPS> (str-compare "string2" "string1")
  1
  CLIPS>

### 12.3.10 Determining the Length of a String

The str-length function returns the integer length of a string.

Syntax

```
(str-length <string-or-symbol-expression>)
```

Example

```
CLIPS> (str-length "abcd")
4
CLIPS> (str-length xyz)
3
CLIPS>
```

### 12.3.11 Checking the Syntax of a Construct or Function Call within a String................

The check-syntax function allows the text representation of a construct or function call to be
checked for syntax and semantic errors.

Syntax

```
(check-syntax <construct-or-function-string>)
```

This function returns the symbol FALSE if there are no errors or warnings encountered parsing
the construct or function call. The symbol MISSING-LEFT-PARENTHESIS is returned if the
first token is not a left parenthesis. The symbol EXTRANEOUS-INPUT-AFTER-LAST-
PARENTHESIS is returned if there are additional tokens after the closing right parenthesis of the
construct or function call. If errors or warnings are encounted parsing, the a multifield of length
two is returned. The first field of the multifield is a string containing the text of the error message
(or the symbol FALSE if no errors were encountered). The second field of the multifield is a string
containing the text of the warning message (or the symbol FALSE if no warnings were
encountered).

```
184 Section 12: Actions and Functions
```

Example

```
CLIPS> (check-syntax "(defrule good =>)")
FALSE
CLIPS> (check-syntax "(defrule bad (number 40000000000000000000) =>)")
(FALSE "[SCANNER1] WARNING: Over or underflow of long long integer.
")
CLIPS> (check-syntax "(defrule bad (3) =>)")
("
[PRNTUTIL2] Syntax Error: Check appropriate syntax for the first field of a
pattern.
```

```
ERROR:
(defrule MAIN::bad
(3
" FALSE)
CLIPS>
```

### 12.3.12 Converting a String to a Field

The string-to-field function parses a string and converts its contents to a primitive data type.

Syntax

```
(string-to-field <string-or-symbol-expression>)
```

The only argument is the string to be parsed. Essentially calling string-to-field with its string
argument is equivalent to calling the read function and manually typing the contents of the string
argument or reading it from a file.

Example

```
CLIPS> (string-to-field "3.4")
3.4
CLIPS> (string-to-field "a b")
a
CLIPS>
```

### 12.3.13 Replacing Portions of a String

The str-replace function will replace all occurrences of a sequence of characters in a string with
another sequence of characters.

Syntax

```
(str-replace <lexeme-expression> <search-expression> <replace-expression>)
```

```
CLIPS Basic Programming Guide 185
```

All three arguments to this function are lexemes. Occurrences of the <search-expression>
argument in the <lexeme-expression> argument are replaced with the <replace-expression>
argument and the new string with replaced sequences is returned.

Example

```
CLIPS> (str-replace "abcdeabcde" "bcd" "xyz")
"axyzeaxyze"
```

### CLIPS>

## 12.4 I/O Functions

CLIPS uses a system called I/O routers which provide a layered mechanism for handling I/O
requests. The router system allows multiple sources to intercept and/or handle a single I/O request.
For example, the batch command redirects input requests from the REPL to a router which reads
input from a file; the dribble-on command intercepts output to the REPL and directs it to a router
which writes output to a file; and the CLIPS Integrated Development Environments for macOS,
Windows, and Java use routers to intercept all console I/O for the REPL and redirect it to the REPL
window for the IDE. CLIPS programs do not directly create routers. Instead routers are indirectly
created by calling system or user defined functions, or by other application code in which CLIPS
has been embedded (such as an IDE). The C API for creating routers is described in the Advanced
Programming Guide.

One of the key concepts of I/O routers is the use of logical names. Logical names allow reference
to an I/O device without having to understand the details of the implementation of the reference.
Many functions in CLIPS make use of logical names. A logical name can be either a symbol, a
number, or a string. Several logical names are predefined by CLIPS and are shown in the following
table.

```
186 Section 12: Actions and Functions
```

```
Name Description
```

```
stdin The default for all user input. The read and readline functions read from stdin if t is specified as the logical name.
```

```
stdout The default for all user functions write to stdoutout if tput is specified as the logical name.. The printout^ and format^
```

```
werror All error messages are sent to this logical name.
wwarning All warning messages are sent to this logical name.
```

### 12.4.1 Opening a File

The open function allows a user to open a file and associate a logical name with it. This function
takes three arguments: (1) the name of the file to be opened; (2) the logical name which will be
used by other CLIPS I/O functions to access the file; and (3) an optional mode specifier. The mode
specifier must be one of the strings from the following table.

```
Mode Means
r Character read access. Specified file must exist.
w Character write access. Existing content overwritten.
a Character write access. Writes append to end of file.
r+ Read and write access. Specified file must exist.
w+ Read and write access. Existing content overwritten.
a+ Read and write access. Writes append to end of file.
```

Binary character mode can also be specified by appending a ‘b’ at the end of the mode or
immediately preceding the ‘+’ character (e.g. rb, rb+, or r+b). If the mode is not specified, it
defaults to character read access.

Syntax

```
(open <file-name> <logical-name> [<mode>])
```

The <file-name> must either be a string or symbol and may include directory specifiers. If a string
is used, the backslash (\) and any other special characters that are part of <file-name> must be
escaped with a backslash. The logical name should not be associated with another open file. The
open function returns the symbol TRUE if it was successful; otherwise, the symbol FALSE is
returned.

```
CLIPS Basic Programming Guide 187
```

Example

```
CLIPS> (open "data.txt" data "w")
TRUE
CLIPS> (close)
TRUE
CLIPS> (open "data.txt" data)
TRUE
CLIPS> (close)
TRUE
CLIPS>
```

### 12.4.2 Closing a File

The close function closes a file stream previously opened with the open command. The file is
specified by a logical name previously attached to the desired stream.

Syntax

```
(close [<logical-name>])
```

If close is called without arguments, all open files will be closed. CLIPS will attempt to close all
open files when the exit command is executed, however, programs should explicitly close files
before exiting to ensure that output is saved. The close function returns the symbol TRUE if any
files were successfully closed; otherwise the symbol FALSE is returned.

Example

```
CLIPS> (open "data.txt" data "w")
TRUE
CLIPS> (close data)
TRUE
CLIPS> (close data)
FALSE
CLIPS> (open "data.txt" data)
TRUE
CLIPS> (close)
TRUE
CLIPS> (close)
FALSE
CLIPS>
```

### 12.4.3 Printing

The printout function allows output to a destination associated with a logical name. The logical
name must be specified and the destination must have been prepared previously for output (e.g., a
file must be opened first). The logical name t may be used instead of stdout to send output to

```
188 Section 12: Actions and Functions
```

standard output (the REPL). If the logical name nil is used, the printout function does nothing; if
the logical name is variable rather than a constant, this allows you to easily disable output by
assigning the value nil to the variable.

The print and println functions are variants of the printout function. Both function always direct
output to stdout and the println function appends a carriage return/line feed after printing all of
its arguments.

Syntax

```
(printout <logical-name> <expression>*)
(print <expression>*)
(println <expression>*)
```

Any number of expressions may be placed in a printout call. Each expression is evaluated and
printed (with no spaces added between each printed expression). The symbol crlf used as an
<expression> will force a carriage return/newline and may be placed anywhere in the list of
expressions to be printed. Similarly, the symbols tab, vtab, and ff will print respectively a tab, a
vertical tab, and a form feed. The appearance of these special symbols may vary from one operating
system to another. The printout function strips quotation marks from around strings when it prints
them. This function has no return value.

Example

```
CLIPS> (printout t "Hello World!" crlf)
Hello World!
CLIPS> (println "Hello World!")
Hello World!
CLIPS> (print "Hello World!" crlf)
Hello World!
CLIPS> (open "data.txt" data "w")
TRUE
CLIPS> (printout data "red green")
CLIPS> (close)
TRUE
CLIPS>
```

### 12.4.4 Reading a Single Field

The read function allows the input of a single field from a source associated with a logical name.
All of the standard restrictions for a field (e.g., multiple symbols must be embedded within quotes)
apply.

Syntax

```
(read [<logical-name>])
```

```
CLIPS Basic Programming Guide 189
```

The <logical-name> term is an optional parameter. If specified, read requests input from the
source associated with the logical name. If the <logical-name> parameter is t or unspecified, the
function will request input from stdin. All the delimiters defined in section 2.3.1 can be used as
delimiters. The read function always returns a primitive data type. Spaces, carriage returns, and
tabs only act as delimiters and are not contained within the return value (unless these characters
are included within double quotes as part of a string). If the end of file is encountered while reading,
read will return the symbol EOF and the get-error function (if called) will return the symbol
EOF. If errors are encountered while reading, the symbol FALSE will be returned and the get-
error function (if called) will return an error code (other than the symbol FALSE).

Example 1

```
CLIPS> (open "data.txt" data "w")
TRUE
CLIPS> (printout data "red green")
CLIPS> (close)
TRUE
CLIPS> (open "data.txt" data)
TRUE
CLIPS> (read data)
red
CLIPS> (get-error)
FALSE
CLIPS> (read data)
green
CLIPS> (read data)
EOF
CLIPS> (get-error)
EOF
CLIPS> (close)
TRUE
CLIPS>
```

Example 2

```
CLIPS> (clear)
CLIPS>
(defrule get-name
=>
(print "What is your first name? ")
(bind ?first (read))
(print "What is your last name? ")
(bind ?last (read))
(assert (name ?first ?last)))
CLIPS>
(defrule print-name
(name ?first ?last)
=>
(println "Hello " ?first " " ?last "."))
CLIPS> (run)
What is your first name? Jack
```

```
190 Section 12: Actions and Functions
```

```
What is your last name? Smith
Hello Jack Smith.
CLIPS>
```

### 12.4.5 Reading an Entire Line

The readline function is similar to the read function, but it reads an entire line of input instead of
a single field. Normally, read will stop when it encounters a delimiter. The readline function only
stops when it encounters a carriage return, a semicolon, or the end of file. Any tabs or spaces in
the input are returned by readline as a part of the string. The readline function returns a string.

Syntax

```
(readline [<logical-name>])
```

The <logical-name> term is an optional parameter. If specified, readline requests input from the
source associated with the logical name. If the <logical-name> parameter is t or unspecified, the
function will request input from stdin. If an end of file (EOF) is encountered while reading,
readline will return the symbol EOF. If errors are encountered while reading, the symbol FALSE
will be returned.

Example 1

```
CLIPS> (open "data.txt" data "w")
TRUE
CLIPS> (printout data "red green")
CLIPS> (close)
TRUE
CLIPS> (open "data.txt" data)
TRUE
CLIPS> (readline data)
"red green"
CLIPS> (readline data)
EOF
CLIPS> (close)
TRUE
CLIPS>
```

Example 2

```
CLIPS> (clear)
CLIPS>
(defrule get-name
=>
(print "What is your name? ")
(bind ?name (readline))
(assert (name ?name)))
CLIPS>
(defrule print-name
(name ?name)
```

```
CLIPS Basic Programming Guide 191
```

```
=>
(println "Hello " ?name "."))
CLIPS> (run)
What is your name? Jack Smith
Hello Jack Smith.
CLIPS>
```

### 12.4.6 Formatted Printing

The format function allows formatted output to be sent to a destination associated with a logical
name. It can be used in place of printout when special formatting of output information is desired.
The format function is similar to the printf function in C. The format function always returns a
string containing the formatted output. A logical name of nil may be used when the formatted
return string is desired without sending output to a destination.

Syntax

```
(format <logical-name> <string-expression> <expression>*)
```

If the symbol t is specified as the <logical-name> parameter, output is sent to stdout. The second
argument to format, called the control string, specifies how the output should be formatted.
Subsequent arguments to format (the parameter list for the control string) are the expressions
which are to be output as indicated by the control string. The format function does not allow
expressions returning multifield values to be included in the parameter list.

The control string consists of text and format flags. Text is output exactly as specified, and format
flags describe how each parameter in the parameter list is to be formatted. The first format flag
corresponds to the first value in the parameter list, the second flag corresponds to the second value,
etc. The format flags must be preceded by a percent sign (%) and use the general format shown
following.

%-M.Nx

The x placeholder is one of the flags listed in the following table, the minus sign is an optional
justification flag, and M and N are optional parameters which specify the field width and the
precision argument (which varies in meaning based on the format flag). If M is used, at least M
characters will be output. If more than M characters are required to display the value, format
expands the field as needed. If M starts with a 0 (e.g., %07d), a zero is used as the pad character;
otherwise, spaces are used. If N is not specified, it defaults to six digits for floating-point numbers.
If a minus sign is included before the M, the value will be left justified; otherwise the value is right
justified.

```
192 Section 12: Actions and Functions
```

```
Format
Flag Meaning^
c Display parameter as a single character.
```

```
d Display parameter as a long longnumber of digits to be printed.) integer. (The N specifier is the minimum
```

```
f Display parameter as a floatingnumber of digits following the decimal point).-point number (The N specifier is the
```

```
e Display parameter as a floatingspecifier is the number of digits following the decimal point).-point using power of 10 notation (The N
```

```
g Display parameter in the most general format, whichever is shorter (the N specifier is the number of significant digits to be printed).
```

```
o Display parameter as an minimum number of digits to be printed.)unsigned octal number. (The N specifier is the
```

```
x Display parameter as an unsigned hexadecimal number. (The N specifier is the minimum number of digits to be printed.)
```

```
s
```

```
Display parameter as a string. Strings will have the leading and trailing
quotes stripped. (The N specifier indicates the maximum number of
characters to be printed. Zero cannot be used for the pad character.)
n Put a new line in the output.
r Put a carriage return in the output.
% Put the percent character in the output.
```

Example

```
CLIPS> (format t "Hello World!%n")
Hello World!
"Hello World!
"
CLIPS> (format nil "Integer: |%d|" 12)
"Integer: |12|"
CLIPS> (format nil "Integer: |%4d|" 12)
"Integer: | 12|"
CLIPS> (format nil "Integer: |%-04d|" 12)
"Integer: |12 |"
CLIPS> (format nil "Integer: |%6.4d|" 12)
"Integer: | 0012|"
CLIPS> (format nil "Float: |%f|" 12.01)
"Float: |12.010000|"
CLIPS> (format nil "Float: |%7.2f| "12.01)
"Float: | 12.01| "
CLIPS> (format nil "Test: |%e|" 12.01)
"Test: |1.201000e+01|"
```

```
CLIPS Basic Programming Guide 193
```

```
CLIPS> (format nil "Test: |%7.2e|" 12.01)
"Test: |1.20e+01|"
CLIPS> (format nil "General: |%g|" 1234567890)
"General: |1.23457e+09|"
CLIPS> (format nil "General: |%6.3g|" 1234567890)
"General: |1.23e+09|"
CLIPS> (format nil "Hexadecimal: |%x|" 12)
"Hexadecimal: |c|"
CLIPS> (format nil "Octal: |%o|" 12)
"Octal: |14|"
CLIPS> (format nil "Symbols: |%s| |%s|" value-a1 capacity)
"Symbols: |value-a1| |capacity|"
CLIPS>
```

❖ Portability Note

The format function is implemented using the ANSI C function sprintf.

### 12.4.7 Renaming a File

The rename function is used to change the name of a file.

Syntax

```
(rename <old-file-name> <new-file-name>)
```

Both <old-file-name> and <new-file-name> must either be a string or symbol and may include
directory specifiers. If a string is used, the backslash (\) and any other special characters that are
part of either <old-file-name> or <new-file-name> must be escaped with a backslash. The rename
function returns the symbol TRUE if it was successful; otherwise, the symbol FALSE is returned.

❖ Portability Note

The rename function is implemented using the ANSI C function rename.

### 12.4.8 Removing a File

The remove function is used to delete a file.

Syntax

```
(remove <file-name>)
```

The <file-name> must either be a string or symbol and may include directory specifiers. If a string
is used, the backslash (\) and any other special characters that are part of <file-name> must be

```
194 Section 12: Actions and Functions
```

escaped with a backslash. The remove function returns the symbol TRUE if it was successful;
otherwise, the symbol FALSE is returned.

❖ Portability Note

The remove function is implemented using the ANSI C function remove.

### 12.4.9 Reading a Character

The get-char function allows a single character to be retrieved from an input source.

Syntax

```
(get-char [<logical-name>])
```

The <logical-name> term is an optional parameter. If specified, get-char tries to retrieve a
character from the specified logical file name. If <logical-name> is the symbol t or is not specified,
the function will read from stdin. The return value is the integer ASCII value of the character
retrieved. The integer - 1 is returned if the end of file is encountered while retrieving a character.

Example

```
CLIPS> (open data.txt data "w")
TRUE
CLIPS> (printout data "ABC" crlf)
CLIPS> (close data)
TRUE
CLIPS> (open data.txt data)
TRUE
CLIPS> (get-char data)
65
CLIPS> (format nil "%c" (get-char data))
"B"
CLIPS> (get-char data)
67
CLIPS> (get-char data)
10
CLIPS> (get-char data)
```

- 1
  CLIPS>
  (progn (print "Press any character to continue...")
  (get-char t))
  Press any character to continue...
  13
  CLIPS> (close)
  TRUE
  CLIPS>

```
CLIPS Basic Programming Guide 195
```

### 12.4.10 Unreading a Character

The unget-char function allows a single character to be returned to an input source.

Syntax

```
(unget-char [<logical-name>] <character>)
```

The <logical-name> term is an optional parameter and <character> is an integer ASCII value of a
character. If <logical-name> is specified, unget-char tries to return <character> to the input source
associated with the logical name. If <logical-name> is the symbol t or is not specified, the function
will return the character to stdin. If successful, the return value is the integer ASCII value of the
character returned; otherwise, the integer - 1 is returnd.

Example

```
CLIPS> (open data.txt data "w")
TRUE
CLIPS> (printout data "ABC" crlf)
CLIPS> (close data)
TRUE
CLIPS> (open data.txt data)
TRUE
CLIPS> (get-char data)
65
CLIPS> (unget-char data 65)
65
CLIPS> (get-char data)
65
CLIPS> (get-char data)
66
CLIPS> (unget-char data 68)
68
CLIPS> (get-char data)
68
CLIPS> (get-char data)
67
CLIPS> (close)
TRUE
CLIPS>
```

### 12.4.11 Reading a Number

The read-number function allows input of a single number using the localized format (if one has
been specified using the set-locale function). If a localized format has not been specified, then the
C format for a number is used.

```
196 Section 12: Actions and Functions
```

Syntax

```
(read-number [<logical-name>])
```

The <logical-name> term is an optional parameter. If specified, read-number attempts to read
from the source associated with the logical file name. If <logical-name> is the symbol t or is not
specified, the function will read from stdin. If a number is successfully parsed, the read-number
function will return either an integer (if the number contained just a sign and digits) or a float (if
the number contained the localized decimal point character or an exponent). If an end of file is
encountered while reading, read-number will return the symbol EOF. If errors are encountered
while reading, the symbol FALSE is returned.

Example

```
CLIPS> (read-number)
34
34
CLIPS> (read-number)
34.0
34.0
CLIPS> (read-number)
8x8
FALSE
CLIPS>
```

### 12.4.12 Setting the Locale

The set-locale function allows the locale to be specified which affects the numeric format behavior
of the format and read-number functions. Before a number is printed by the format function or
is parsed by the read-number function, the locale is temporarily changed to the last value specified
to the set-locale function (or the default C locale if no value was previously specified).

Syntax

```
(set-locale [<locale-string>])
```

The optional parameter <locale-string> is a string containing the new locale to be used by the
format and read-number functions. If <local-string> is specified, then the value of the previous
locale is returned. If <locale-string> is not specified, then the value of the current locale is returned.
A <locale-string> value of "" uses the native locale (and the specification of this locale is
dependent on the environment in which CLIPS is run). A <locale-string> of "C" specifies the
standard C locale (which is the default).

Example

```
CLIPS> (set-locale)
C
```

```
CLIPS Basic Programming Guide 197
```

```
CLIPS> (read-number)
12.1
12.1
CLIPS> (read-number)
12,1
FALSE
CLIPS> (format nil "%f" 12.1)
"12.100000"
CLIPS> (set-locale "de_DE") ; macOS
C
CLIPS> (read-number)
12.1
FALSE
CLIPS> (read-number)
12,1
12.1
CLIPS> (format nil "%f" 12.1)
"12,100000"
CLIPS> (set-locale)
"de_DE"
CLIPS> (set-locale "C")
"de_DE"
CLIPS>
```

❖ Portability Note

The CLIPS set-locale function uses the ANSI C function setlocale to temporarily change the
locale. The value used to set a specific local can vary. For example, in Windows the <local-string>
for Germany is “DE” and in macOS, the <locale-string> for Germany is “de_DE”.

### 12.4.13 Flushing Output

The flush function writes pending output to a file stream previously opened with the open com-
mand. The file is specified by a logical name previously associated with the file stream. Flushed
files remain open. Typically output does not need to be flushed since closing the file with the close
command will flush pending output.

Syntax

```
(flush [<logical-name>])
```

If flush is called without arguments, all open files will be flushed. The flush function returns the
symbol TRUE if any files were successfully flushed; otherwise, the symbol FALSE is returned.

❖ Portability Note

The flush function uses the ANSI C function fflush as a base.

```
198 Section 12: Actions and Functions
```

### 12.4.14 Rewinding the File Position

The rewind function sets the position in a file stream previously opened with the open command
to the beginning of the file. The file is specified by a logical name previously associated with the
file stream.

Syntax

```
(rewind <logical-name>)
```

The rewind function returns the symbol TRUE if successful; otherwise, the symbol FALSE is
returned.

❖ Portability Note

The rewind function uses the ANSI C function rewind as a base.

### 12.4.15 Retrieving the File Position

The tell function returns the current position in a file stream previously opened with the open
command. The file is specified by a logical name previously associated with the file stream.

Syntax

```
(tell <logical-name>)
```

The tell function returns the integer file position if successful; otherwise, the symbol FALSE is
returned.

❖ Portability Note

The tell function uses the ANSI C function ftell as a base.

### 12.4.16 Setting the File Position

The seek function sets the current position in a file stream previously opened with the open
command. The file is specified by a logical name previously associated with the file stream.

Syntax

```
(seek <logical-name> <offset> <relative-position)
```

The <offset> argument is an integer value and the <relative-position> argument is one of the
symbols seek-set, seek-cur, or seek-end. If seek-set is specified, the file position is set based on

```
CLIPS Basic Programming Guide 199
```

the offset relative to the beginning of the file. If seek-cur is specified, the file position is set based
on the offset relative to the current positiion in the file. If seek-end is specified, the file position is
set based on the offset relative to the end of the file. The seek function returns the symbol TRUE
if the file position was successfully set; otherwise the symbol FALSE is returned.

❖ Portability Note

The seek function uses the ANSI C function fseek as a base.

### 12.4.17 Changing the Current Directory..........................................................................

The chdir function changes the current directory.

Syntax

```
(chdir [<path>])
```

The optional <path> argument is a string or symbol value containing the path to the new directory
(either absolute or relative). If the <path> argument is unspecified, then the function returns the
symbol TRUE if the system supports the chdir function; otherwise, the symbol FALSE is
returned. If the <path> argument is specified, then the function returns the symbol TRUE if the
directory was successfully changed; otherwise, the symbol FALSE is returned.

❖ Portability Note

The chdir function uses the C function chdir as a base on macOS and Linux and the C function
\_wchdir as a base on Windows. This function is not supported on other platforms.

## 12.5 Math Functions

CLIPS provides numerous functions for mathematical computations. They are split into two sets:
a set of standard math functions and a set of extended math functions.

The standard math functions are listed below. These functions should be used only on numeric
arguments. An error message will be printed if a string argument is passed to a math function.

### 12.5.1 Addition

The + function returns the sum of its arguments. Each of its arguments should be a numeric
expression. Addition is performed using the type of the arguments provided unless mixed mode
arguments (integer and float) are used. In this case, the function return value and integer arguments

```
200 Section 12: Actions and Functions
```

are converted to floats after the first float argument has been encountered. This function returns a
float if any of its arguments is a float; otherwise, it returns an integer.

Syntax

```
(+ <numeric-expression> <numeric-expression>+)
```

Example

```
CLIPS> (+ 2 3 4)
9
CLIPS> (+ 2 3.0 5)
10.0
CLIPS> (+ 3.1 4.7)
7.8
CLIPS>
```

### 12.5.2 Subtraction

The - function returns the value of the first argument minus the sum of all subsequent arguments.
Each of its arguments should be a numeric expression. Subtraction is performed using the type of
the arguments provided unless mixed mode arguments (integer and float) are used. In this case,
the function return value and integer arguments are converted to floats after the first float argument
has been encountered. This function returns a float if any of its arguments is a float; otherwise, it
returns an integer.

Syntax

```
(- <numeric-expression> <numeric-expression>+)
```

Example

```
CLIPS> (- 12 3 4)
5
CLIPS> (- 12 3.0 5)
4.0
CLIPS> (- 4.7 3.1)
1.6
CLIPS>
```

### 12.5.3 Multiplication

The \* function returns the product of its arguments. Each of its arguments should be a numeric
expression. Multiplication is performed using the type of the arguments provided unless mixed
mode arguments (integer and float) are used. In this case, the function return value and integer
arguments are converted to floats after the first float argument has been encountered. This function
returns a float if any of its arguments is a float; otherwise, it returns an integer.

```
CLIPS Basic Programming Guide 201
```

Syntax

```
(* <numeric-expression> <numeric-expression>+)
```

Example

```
CLIPS> (* 2 3 4)
24
CLIPS> (* 2 3.0 5)
30.0
CLIPS> (* 3.1 4.7)
14.57
CLIPS>
```

12.5.4 Division

The / function returns the value of the first argument divided by each of the subsequent arguments.
Each of its arguments should be a numeric expression. Each argument is automatically converted
to a float and floating point division is performed. This function returns a float.

Syntax

```
(/ <numeric-expression> <numeric-expression>+)
```

Example

```
CLIPS> (/ 4 2)
2.0
CLIPS> (/ 4.0 2.0)
2.0
CLIPS> (/ 24 3 4)
2.0
CLIPS>
```

### 12.5.5 Integer Division

The div function returns the value of the first argument divided by each of the subsequent
arguments. Each of its arguments should be a numeric expression. Each argument is automatically
converted to an integer and integer division is performed. This function returns an integer.

Syntax

```
(div <numeric-expression> <numeric-expression>+)
```

Example

```
CLIPS> (div 4 2)
2
```

```
202 Section 12: Actions and Functions
```

```
CLIPS> (div 5 2)
2
CLIPS> (div 33 2 3 5)
1
CLIPS>
```

### 12.5.6 Maximum Numeric Value

The max function returns the value of its largest numeric argument. Each of its arguments should
be a numeric expression. When necessary, integers are temporarily converted to floats for
comparison. The return value will either be integer or float (depending upon the type of the largest
argument).

Syntax

```
(max <numeric-expression>+)
```

Example

```
CLIPS> (max 3.0 4 2.0)
4
CLIPS>
```

### 12.5.7 Minimum Numeric Value

The min function returns the value of its smallest numeric argument. Each of its arguments should
be a numeric expression. When necessary, integers are temporarily converted to floats for
comparison. The return value will either be integer or float (depending upon the type of the
smallest argument).

Syntax

```
(min <numeric-expression>+)
```

Example

```
CLIPS> (min 4 0.1 -2.3)
```

- 2.3
  CLIPS>

### 12.5.8 Absolute Value......................................................................................................

The abs function returns the absolute value of its only argument (which should be a numeric
expression). The return value will either be integer or float (depending upon the type the
argument).

```
CLIPS Basic Programming Guide 203
```

Syntax

```
(abs <numeric-expression>)
```

Example

```
CLIPS> (abs 4.0)
4.0
CLIPS> (abs -2)
2
CLIPS>
```

### 12.5.9 Convert To Float

The float function converts its only argument (which should be a numeric expression) to type float
and returns this value.

Syntax

```
(float <numeric-expression>)
```

Example

```
CLIPS> (float 4.0)
4.0
CLIPS> (float -2)
```

- 2.0
  CLIPS>

### 12.5.10 Convert To Integer

The integer function converts its only argument (which should be a numeric expression) to type
integer and returns this value.

Syntax

```
(integer <numeric-expression>)
```

Example

```
CLIPS> (integer 4.0)
4
CLIPS> (integer -2)
```

- 2
  CLIPS>

```
204 Section 12: Actions and Functions
```

### 12.5.11 Trigonometric Functions

The following trigonometric functions take one numeric argument and return a floating-point
number. The argument is expected to be in radians.

```
Function Returns
acos arccosine
acot arccotangent
acsc arccosecant
asec arcsecant
asin arcsine
atan arctangent
cos cosine
cot cotangent
csc cosecant
sec secant
sin sine
tan tangent
```

```
Function Returns
acosh hyperbolic arccosine
acoth hyperbolic arccotangent
acsch hyperbolic arccosecant
asech hyperbolic arcsecant
asinh hyperbolic arcsine
atanh hyperbolic arctangent
cosh hyperbolic cosine
coth hyperbolic cotangent
csch hyperbolic cosecant
sech hyperbolic secant
sinh hyperbolic sine
tanh hyperbolic tangent
```

Example

```
CLIPS> (cos 0)
1.0
CLIPS> (acos 1.0)
0.0
CLIPS>
```

12.5.11.1 Two Argument Arctangent

The atan2 function returns the arctangent of the value y/x where the arguments represent the point
(x,y) in a Cartesian coordinate system.

Syntax

```
(atan2 <y-numeric-expression> <x-numeric-expression>)
```

Example

```
CLIPS> (atan -1)
```

```
CLIPS Basic Programming Guide 205
```

- 0.785398163397448
  CLIPS> (atan2 1 -1)
  2.35619449019234
  CLIPS> (atan2 -1 1)
- 0.785398163397448
  CLIPS>

### 12.5.12 Convert From Degrees to Grads

The deg-grad function converts its only argument (which should be a numeric expression) from
units of degrees to units of grads (360 degrees = 400 grads). The return value of this function is a
float.

Syntax

```
(deg-grad <numeric-expression>)
```

Example

```
CLIPS> (deg-grad 90)
100.0
CLIPS>
```

### 12.5.13 Convert From Degrees to Radians

The deg-rad function converts its only argument (which should be a numeric expression) from
units of degrees to units of radians (360 degrees = 2π radians). The return value of this function is
a float.

Syntax

```
(deg-rad <numeric-expression>)
```

Example

```
CLIPS> (deg-rad 180)
3.141592653589793
CLIPS>
```

### 12.5.14 Convert From Grads to Degrees

The grad-deg function converts its only argument (which should be a numeric expression) from
units of grads to units of degrees (360 degrees = 400 grads). The return value of this function is a
float.

```
206 Section 12: Actions and Functions
```

Syntax

```
(grad-deg <numeric-expression>)
```

Example

```
CLIPS> (grad-deg 100)
90.0
CLIPS>
```

### 12.5.15 Convert From Radians to Degrees

The rad-deg function converts its only argument (which should be a numeric expression) from
units of radians to units of degrees (360 degrees = 2π radians). The return value of this function is
a float.

Syntax

```
(rad-deg <numeric-expression>)
```

Example

```
CLIPS> (rad-deg 3.141592653589793)
180.0
CLIPS>
```

### 12.5.16 Return the Value of π

The pi function returns the value of π (3.141592653589793...) as a float.

Syntax

```
(pi)
```

Example

```
CLIPS> (pi)
3.141592653589793
CLIPS>
```

### 12.5.17 Square Root

The sqrt function returns the square root of its only argument (which should be a numeric
expression) as a float.

```
CLIPS Basic Programming Guide 207
```

Syntax

```
(sqrt <numeric-expression>)
```

Example

```
CLIPS> (sqrt 9)
3.0
CLIPS>
```

### 12.5.18 Power

The \*\* function raises its first argument to the power of its second argument and returns this value
as a float.

Syntax

```
(** <numeric-expression> <numeric-expression>)
```

Example

```
CLIPS> (** 3 2)
9.0
CLIPS>
```

### 12.5.19 Exponential

The exp function raises the value e (the base of the natural system of logarithms, having a value
of approximately 2.718...) to the power specified by its only argument and returns this value as a
float.

Syntax

```
(exp <numeric-expression>)
```

Example

```
CLIPS> (exp 1)
```

2. 718281828459045
   CLIPS>

### 12.5.20 Logarithm

Given n (the only argument) and the value e is the base of the natural system of logarithms, the
log function returns the float value x such that the following equation is satisfied:

```
208 Section 12: Actions and Functions
```

```
n = ex
```

Syntax

```
(log <numeric-expression>)
```

Example

```
CLIPS> (log 2.718281828459045)
1.0
CLIPS>
```

12.5.21 Logarithm Base 10

Given n (the only argument), the log10 function returns the float value x such that the following
equation is satisfied:

```
n = 10x
```

Syntax

```
(log10 <numeric-expression>)
```

Example

```
CLIPS> (log10 100)
2.0
CLIPS>
```

### 12.5.22 Round

The round function rounds its only argument (which should be a numeric expression) toward the
closest integer. If the argument is exactly between two integers, it is rounded away from zero). The
return value of this function is an integer.

Syntax

```
(round <numeric-expression>)
```

Example

```
CLIPS> (round 3.6)
4
CLIPS>
```

```
CLIPS Basic Programming Guide 209
```

### 12.5.23 Modulus

The mod function returns the remainder of the result of dividing its first argument by its second
argument (assuming that the result of division must be an integer). It returns an integer if both
arguments are integers, otherwise it returns a float.

Syntax

```
(mod <numeric-expression> <numeric-expression>)
```

Example

```
CLIPS> (mod 5 2)
1
CLIPS> (mod 3.7 1.2)
0.1
CLIPS>
```

## 12.6 Procedural Functions

The following are functions which provide procedural programming capabilities similar to
languages such as C and Java.

### 12.6.1 Binding Variables

The bind function allows values to be assigned to variables.

Syntax

```
(bind <variable> <expression>*)
```

The <variable> term is the local or global variable to be bound (which may have been bound
previously). The bind function may also be used within a message-handler’s body to set a slot’s
value.

If no <expression> is specified, then local variables are unbound and global variables are reset to
their original value. If one <expression> is specified, then the value of <variable> is set to the
return value from evaluating <expression>. If more than one <expression> is specified, then all of
the <expressions> are evaluated and grouped together as a multifield value and the resulting value
is stored in <variable>.

The bind function returns the symbol FALSE when a local variable is unbound, otherwise, the
return value is the value to which <variable> is set.

```
210 Section 12: Actions and Functions
```

Example 1

```
CLIPS> (defglobal ?*x* = 3.4)
CLIPS> ?*x*
3.4
CLIPS> (bind ?*x* (+ 8 9))
17
CLIPS> ?*x*
17
CLIPS> (bind ?*x* (create$ a b c d))
(a b c d)
CLIPS> ?*x*
(a b c d)
CLIPS> (bind ?*x* d e f)
(d e f)
CLIPS> ?*x*
(d e f)
CLIPS> (bind ?*x*)
3.4
CLIPS> ?*x*
3.4
CLIPS> (bind ?x 32)
32
CLIPS> ?x
32
CLIPS> (reset)
CLIPS> ?x
[EVALUATN1] Variable x is unbound
FALSE
CLIPS>
```

Example 2

```
CLIPS>
(defclass A (is-a USER)
(slot x)
(slot y))
CLIPS>
(defmessage-handler A init after ()
(bind ?self:x 3)
(bind ?self:y 4))
CLIPS> (make-instance a of A)
[a]
CLIPS> (send [a] print)
[a] of A
(x 3)
(y 4)
CLIPS>
```

### 12.6.2 If...then...else Function..........................................................................................

The if function allows conditional execution of a set of actions.

```
CLIPS Basic Programming Guide 211
```

Syntax

```
(if <expression>
then
<action>*
[else
<action>*])
```

Any number of allowable actions may be used inside of the then or else portion, including another
if...then...else structure. The else portion is optional. If <expression> evaluates to anything other
than the symbol FALSE, then the actions associated with the then portion are executed.
Otherwise, the actions associated with the else portion are executed. The return value of the if
function is the value of the last <expression> or <action> evaluated.

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
(slot age))
CLIPS>
(defrule print-age
(person (name ?name) (age ?age))
=>
(if (= ?age 1)
then
(println ?name " is 1 year old")
else
(println ?name " is " ?age " years old")))
CLIPS> (assert (person (name "Sam Jones") (age 1)))
<Fact-1>
CLIPS> (assert (person (name "Jill Smith") (age 13)))
<Fact-2>
CLIPS> (run)
Jill Smith is 13 years old
Sam Jones is 1 year old
CLIPS>
```

When using the if function in the actions of a rule, one should consider whether shifting the
conditions to separate rules is preferable. For example, the print-age rule in the prior example
could be rewritten as the following two rules.

```
(defrule print-age- 1
(person (name ?name) (age 1))
=>
(println ?name " is 1 year old"))
```

```
(defrule print-age-not- 1
(person (name ?name) (age ?age&~1))
```

```
212 Section 12: Actions and Functions
```

```
=>
(println ?name " is " ?age " years old"))
```

### 12.6.3 While

The while function allows simple looping based on a condition.

Syntax

```
(while <expression> [do]
<action>*)
```

Any number of allowable actions may be placed inside the while block. The <expression> term is
performed prior to the first execution of the loop. The actions within the while loop are executed
until <expression> evaluates to the symbol FALSE. The while may optionally include the symbol
do after the condition and before the first action. The break and return functions can be used to
terminate the loop prematurely. The return value of this function is the symbol FALSE unless the
return function is used to terminate the loop.

Example

```
CLIPS>
(deffunction countdown (?count)
(while (> ?count 0)
(println ?count)
(bind ?count (- ?count 1)))
(return (void)))
CLIPS> (countdown 3)
3
2
1
CLIPS>
```

### 12.6.4 Loop-for-count

The loop-for-count function allows iterative looping.

Syntax

```
(loop-for-count <range-spec> [do] <action>*)
```

```
<range-spec> ::= <end-index> |
(<loop-variable> <start-index> <end-index>) |
(<loop-variable> <end-index>)
<start-index> ::= <integer-expression>
<end-index> ::= <integer-expression>
```

```
CLIPS Basic Programming Guide 213
```

The <action> term is performed the number of times specified by <range-spec>. If <start-index>
is not given, it is assumed to be one. If <start-index> is greater than <end-index>, then the body
of the loop is never executed. The integer value of the current iteration can be examined with the
loop variable, if specified. The break and return functions can be used to terminate the loop
prematurely. The return value of this function is the symbol FALSE unless the return function is
used to terminate the loop. Variables from an outer scope may be used within the loop, but the
loop variable (if specified) masks any outer variables of the same name. Loops can be nested.

Example

```
CLIPS> (loop-for-count 2 (println "Hello World!"))
Hello World!
Hello World!
FALSE
CLIPS>
(loop-for-count (?cnt1 2 4) do
(loop-for-count (?cnt2 1 3) do
(println ?cnt1 " " ?cnt2)))
2 1
2 2
2 3
3 1
3 2
3 3
4 1
4 2
4 3
FALSE
CLIPS>
```

### 12.6.5 Progn

The progn function evaluates all of its arguments and returns the value of the last argument.

Syntax

```
(progn <expression>*)
```

Example

```
CLIPS> (progn (setgen 5) (gensym))
gen5
CLIPS>
```

### 12.6.6 Progn$

The progn$ function performs a set of actions for each field of a multifield value.

```
214 Section 12: Actions and Functions
```

Syntax

```
(progn$ <multifield-spec> <expression>*)
```

```
<multifield-spec> ::= <multifield-expression> |
(<field-variable> <multifield-expression>)
```

The field of the current iteration can be examined with the <field-variable> term, if specified. The
index of the current iteration can be examined with <field-variable>-index. The progn$ function
can use variables from outer scopes, and the return and break functions can also be used within
a progn$ as long as they are valid in the outer scope. The return value of this function is the return
value of the last action performed for the last field in the multifield value.

Example

```
CLIPS>
(progn$ (?item (create$ milk eggs cheese))
(println ?item-index ". " ?item))
```

1. milk
2. eggs
3. cheese
   CLIPS>

### 12.6.7 Return

The return function immediately terminates the currently executing deffunction, generic function
method, message-handler, defrule, or fact/instance set query function. Without any arguments,
there is no return value. However, if an argument is included, its value is the return value of the
deffunction, method, or message-handler in which it is contained. If used in the RHS of a rule, the
current focus is removed from the focus stack.

Syntax

```
(return [<expression>])
```

Example

```
CLIPS>
(deffunction sign (?num)
(if (> ?num 0) then
(return 1))
(if (< ?num 0) then
(return -1))
0)
CLIPS> (sign 5)
1
CLIPS> (sign -10)
```

- 1
  CLIPS> (sign 0)

```
CLIPS Basic Programming Guide 215
```

```
0
CLIPS>
```

### 12.6.8 Break

The break function immediately terminates the currently iterating while loop, loop-for-count
execution, progn execution, progn$ execution, foreach execution, or fact/instance set query
function.

Syntax

```
(break)
```

Example

```
CLIPS>
(deffunction iterate (?num)
(bind ?i 0)
(while TRUE do
(if (>= ?i ?num) then
(break))
(print ?i " ")
(bind ?i (+ ?i 1)))
(println))
CLIPS> (iterate 1)
0
CLIPS> (iterate 10)
0 1 2 3 4 5 6 7 8 9
CLIPS>
```

### 12.6.9 Switch

The switch function selects a particular group of actions (among several groups of actions) to
perform based on a specified value.

Syntax

```
(switch <test-expression>
<case-statement>*
[<default-statement>])
```

```
<case-statement> ::=
(case <comparison-expression> then <action>*)
```

```
<default-statement> ::= (default <action>*)
```

As indicated by the BNF, the optional default statement must succeed all case statements. None of
the case comparison expressions should be the same.

```
216 Section 12: Actions and Functions
```

The switch function evaluates the <test-expression> term first and then evaluates each
<comparison-expression> term in order of definition. Once the evaluation of the
<comparison-expression> is equivalent to the evaluation of the <test-expression>, the actions of
that case are evaluated (in order) and the switch function is terminated. If no cases are satisfied,
the default actions (if any) are evaluated (in order).

The return value of the switch function is the last action evaluated in the switch function. If no
actions are evaluated, the return value is the symbol FALSE.

Example

```
CLIPS>
(deffunction complement (?color)
(switch ?color
(case red then cyan)
(case cyan then red)
(case green then magenta)
(case magenta then green)
(case blue then yellow)
(case yellow then blue)
(default FALSE)))
CLIPS> (complement green)
magenta
CLIPS> (complement black)
FALSE
CLIPS>
```

### 12.6.10 Foreach

The foreach function performs a set of actions for each field of a multifield value.

Syntax

```
(foreach <field-variable> <multifield-expression> <expression>*)
```

The field of the current iteration can be examined with the <field-variable> term if specified. The
index of the current iteration can be examined with <field-variable>-index. The foreach function
can use variables from outer scopes, and the return and break functions can also be used within
a foreach as long as they are valid in the outer scope. The return value of this function is the return
value of the last action performed for the last field in the multifield value.

Example

```
CLIPS>
(foreach ?item (create$ milk eggs cheese)
(println ?item-index ". " ?item))
```

```
CLIPS Basic Programming Guide 217
```

1. milk
2. eggs
3. cheese
   CLIPS>

❖ Portability Note

The foreach function provides the same functionality as the progn$ function, but uses different
syntax with a more meaningful function name.

## 12.7 Miscellaneous Functions

The following are additional functions for use within CLIPS.

### 12.7.1 Gensym

The gensym function returns a sequenced generated symbol that can be stored as a single field.
This is useful for slot values that need a simple identifier. Multiple calls to gensym return different
identifiers of the form genX where X is a positive integer. The first call to gensym returns gen1;
all subsequent calls increment the number. Note that gensym is not reset after a call to clear. If
users plan to use the gensym feature, they should avoid creating facts which include a user-defined
field of this form.

Example

```
CLIPS>
(deftemplate order
(slot id (default-dynamic (gensym)))
(slot item)
(slot quantity))
CLIPS> (assert (order (item C3) (quantity 3)))
<Fact-1>
CLIPS> (assert (order (item B1) (quantity 1)))
<Fact-2>
CLIPS> (assert (order (item C3) (quantity 3)))
<Fact-3>
CLIPS> (facts)
f-1 (order (id gen1) (item C3) (quantity 3))
f-2 (order (id gen2) (item B1) (quantity 1))
f-3 (order (id gen3) (item C3) (quantity 3))
For a total of 3 facts.
CLIPS>
```

```
218 Section 12: Actions and Functions
```

### 12.7.2 Gensym\*

The gensym\* function is similar to the gensym function, however, it will produce a unique symbol
that does not currently exist within the CLIPS environment.

Example

```
CLIPS> (setgen 1)
1
CLIPS> (assert (gen1 gen2 gen3))
<Fact- 1 >
CLIPS> (gensym)
gen1
CLIPS> (gensym*)
gen4
CLIPS>
```

### 12.7.3 Setgen

The setgen function assigns the starting integer used by the gensym and gensym\* functions.

Syntax

```
(setgen <integer-expression>)
```

The <intger-expression> term must be a positive integer value and is the value returned by this
function. All subsequent calls to gensym will return a sequenced symbol with the numeric portion
of the symbol starting at <integer-expression>.

Example

```
CLIPS> (setgen 32)
32
CLIPS> (gensym)
gen32
CLIPS>
```

### 12.7.4 Random

The random function returns a random integer value.

Syntax

```
(random [<start-integer-expression> <end-integer-expression>])
```

The <start-integer-expression> and <end-integer-expression> terms, if specified, indicate the
range of values to which the randomly generated integer is limited.

```
CLIPS Basic Programming Guide 219
```

Example

```
CLIPS> (clear)
CLIPS>
(defrule roll-the-dice
?f <- (roll-the-dice)
=>
(retract ?f)
(bind ?roll1 (random 1 6))
(bind ?roll2 (random 1 6))
(println "Your roll is: " ?roll1 " " ?roll2))
CLIPS> (assert (roll-the-dice))
<Fact-1>
CLIPS> (run)
Your roll is: 5 6
CLIPS>
```

❖ Portability Note

The rand function is implemented using the ANSI C function rand.

### 12.7.5 Seed

The seed function seeds the random number generator.

Syntax

```
(seed <integer-expression>)
```

The <integer-expression> term is the integer seed value. This function has no return value.

Example

```
CLIPS> (seed 2357)
CLIPS> (random 1 10)
10
CLIPS> (random 1 10)
4
CLIPS> (random 1 10)
2
CLIPS> (seed 2357)
CLIPS> (random 1 10)
10
CLIPS> (random 1 10)
4
CLIPS> (random 1 10)
2
CLIPS>
```

```
220 Section 12: Actions and Functions
```

❖ Portability Note

The seed function is implemented using the ANSI C function srand. The CLIPS Integrated
Development Environments for Windows, macOS, and Java use a multi-threaded implementation;
the user interface runs on the main thread and each command entered at the Read-Eval-Print Loop
is executed using a separate newly created thread. In this situation, the seed function (via srand)
is not guaranteed to properly seed the random number generator for newly created threads (i.e.
subsequent commands entered at the REPL).

### 12.7.6 Time

The time function returns a floating-point value representing the elapsed seconds since the system
reference time.

Syntax

```
(time)
```

### 12.7.7 Determining the Restrictions for a Function

The get-function-restrictions function can be used to gain access to the restriction string
associated with a system or user defined function created using the AddUDF API. The restriction
string contains information on the number and types of arguments that a function expects. The
restriction string contains the minimum number of arguments, maximum number of arguments,
default argument type, and specific argument types. Each entry in the restriction string is delimited
by a semicolon. See section 8 of the Advanced Programming Guide for the meaning of the
characters which compose the restriction string.

Syntax

```
(get-function-restrictions <function-name>)
```

Example

```
CLIPS> (get-function-restrictions +)
"2;*;ld"
CLIPS>
```

### 12.7.8 Sorting a List of Values

The sort function allows a list of values to be sorted.

Syntax

```
(sort <comparison-function-name> <expression>*)
```

```
CLIPS Basic Programming Guide 221
```

The sort function returns a multifield value containing the sorted values specified as arguments.
The comparison function used for sorting should accept exactly two arguments and can be a user-
defined function, a generic function, or a deffunction. Given two adjacent arguments from the list
to be sorted, the comparison function should return the symbol TRUE if its first argument should
come after its second argument in the sorted list; otherwise, the symbol FALSE should be returned.

Example

```
CLIPS> (sort > 4 3 5 7 2 7)
(2 3 4 5 7 7)
CLIPS>
(deffunction string> (?a ?b)
(> (str-compare ?a ?b) 0))
CLIPS> (sort string> ax aa bk mn ft m)
(aa ax bk ft m mn)
CLIPS>
```

### 12.7.9 Calling a Function

The funcall function constructs a function call from its arguments and then evaluates the function
call. The first argument should be the name of a user-defined function, deffunction, or generic
function. The remaining arguments are evaluated and then passed to the specified function when
it is evaluated. Functions that are invoked using specialized syntax, such as the assert command
(which uses parentheses to delimit both slot and function names), may not be called using funcall.

Syntax

```
(funcall <function-name> <expression>*)
```

Example

```
CLIPS> (funcall delete$ (create$ a b c) 2 2)
(a c)
CLIPS> (funcall + 1 2 (expand$ (create$ 3 4)))
10
CLIPS>
```

### 12.7.10 Timing Functions and Commands

The timer function returns the number of seconds elapsed evaluating a series of expressions.

Syntax

```
(timer <expression>*)
```

```
222 Section 12: Actions and Functions
```

Example

```
CLIPS> (timer (loop-for-count 10000 (+ 3 4)))
0.0416709999999512
CLIPS>
```

### 12.7.11 Determining the Operating System

The operating-system function returns a symbol indicating the opertating system on which CLIPS
is running. Possible return values are the symbols UNIX-V, UNIX- 7 , LINUX, DARWIN,
MAC-OS, DOS, WINDOWS, and UNKNOWN.

Syntax

```
(operating-system)
```

12.7.12 Local Time

The local-time function returns a multifield value containing fields indicating the local time. In
order, the returned fields are year, month, day, hours, seconds, day of week, days since the
beginning of the year, and a boolean flag indicating whether daylight savings time is in effect.

Syntax

```
(local-time)
```

Example

```
CLIPS> (local-time)
(2018 6 6 15 1 9 Wednesday 156 TRUE)
CLIPS>
```

### 12.7.13 Greenwich Mean Time

The gm-time function returns returns a multifield value containing fields indicating Greenwich
mean time. In order, the returned fields are year, month, day, hours, seconds, day of week, days
since the beginning of the year, and a boolean flag indicating whether daylight savings time is in
effect.

Syntax

```
(gm-time)
```

Example

```
CLIPS> (gm-time)
```

```
CLIPS Basic Programming Guide 223
```

```
(2018 6 6 20 1 44 Wednesday 156 FALSE)
CLIPS>
```

### 12.7.14 Getting the Error State

The get-error function returns the current value of the error state (or status value). The error state
can be set by system and user defined functions as well as using the set-error function.

Syntax

```
(get-error)
```

### 12.7.15 Clearing the Error State

The clear-error function resets the error state (or status value) to the the symbol FALSE and
returns the prior value of the error state.

Syntax

```
(clear-error)
```

### 12.7.16 Setting the Error State

The set-error function sets the error state (or status value).

Syntax

```
(set-error <expression>)
```

Example

```
CLIPS> (set-error 10)
CLIPS> (get-error)
10
CLIPS> (get-error)
10
CLIPS> (clear-error)
10
CLIPS> (get-error)
FALSE
CLIPS>
```

### 12.7.17 Void Value

The void function returns the void value.

```
224 Section 12: Actions and Functions
```

Syntax

```
(void)
```

Example

```
CLIPS>
(deffunction countdown (?c)
(loop-for-count (?i 0 ?c) (println (- ?c ?i))))
CLIPS> (countdown 3)
3
2
1
0
FALSE
CLIPS>
(deffunction countdown (?c)
(loop-for-count (?i 0 ?c) (println (- ?c ?i)))
(void))
CLIPS> (countdown 3)
3
2
1
0
CLIPS>
```

## 12.8 Deftemplate Functions

The following functions provide ancillary capabilities for the deftemplate construct.

### 12.8.1 Determining the Module in which a Deftemplate is Defined

The deftemplate-module function returns the module in which the specified deftemplate name is
defined.

Syntax

```
(deftemplate-module <deftemplate-name>)
```

### 12.8.2 Getting the Allowed Values for a Deftemplate Slot

The deftemplate-slot-allowed-values function groups the allowed values for a slot (specified in
any of allowed-... attributes for the slots) into a multifield variable. If no allowed-... attributes
were specified for the slot, then the symbol FALSE is returned. A multifield of length zero is
returned if an error occurs.

```
CLIPS Basic Programming Guide 225
```

Syntax

```
(deftemplate-slot-allowed-values <deftemplate-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot gender (allowed-symbols male female)))
CLIPS> (deftemplate-slot-allowed-values person gender)
(male female)
CLIPS>
```

### 12.8.3 Getting the Cardinality for a Deftemplate Slot

The deftemplate-slot-cardinality function groups the minimum and maximum cardinality
allowed for a multifield slot into a multifield variable. A maximum cardinality of infinity is
indicated by the symbol +oo (the plus character followed by two lowercase o’s—not zeroes). A
multifield of length zero is returned for single field slots or if an error occurs.

Syntax

```
(deftemplate-slot-cardinality <deftemplate-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate polygon
(multislot coordinates
(type INTEGER)
(cardinality 6 ?VARIABLE)))
CLIPS> (deftemplate-slot-cardinality polygon coordinates)
(6 +oo)
CLIPS>
```

### 12.8.4 Testing whether a Deftemplate Slot has a Default................................................

The deftemplate-slot-defaultp function returns the symbol static if the specified slot in the
specified deftemplate has a static default (whether explicitly or implicitly defined), the symbol
dynamic if the slot has a dynamic default, or the symbol FALSE if the slot does not have a default.
An error is generated if the specified deftemplate or slot does not exist.

Syntax

```
(deftemplate-slot-defaultp <deftemplate-name> <slot-name>)
```

```
226 Section 12: Actions and Functions
```

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate order
(slot id (default-dynamic (gensym)))
(slot item (type STRING) (default ?NONE))
(slot quantity (type INTEGER) (default 1))
(slot details (type STRING)))
CLIPS> (deftemplate-slot-defaultp order id)
dynamic
CLIPS> (deftemplate-slot-defaultp order item)
FALSE
CLIPS> (deftemplate-slot-defaultp order quantity)
static
CLIPS> (deftemplate-slot-defaultp order details)
static
CLIPS>
```

### 12.8.5 Getting the Default Value for a Deftemplate Slot

The deftemplate-slot-default-value function returns the default value associated with a
deftemplate slot. If a slot has a dynamic default, the expression will be evaluated when this function
is called. The symbol FALSE is returned if an error occurs.

Syntax

```
(deftemplate-slot-default-value <deftemplate-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate order
(slot id (default-dynamic (gensym)))
(slot item (type STRING) (default ?NONE))
(slot quantity (type INTEGER) (default 1))
(slot details (type STRING)))
CLIPS> (deftemplate-slot-default-value order id)
gen1
CLIPS> (deftemplate-slot-default-value order item)
?NONE
CLIPS> (deftemplate-slot-default-value order quantity)
1
CLIPS> (deftemplate-slot-default-value order details)
""
CLIPS>
```

```
CLIPS Basic Programming Guide 227
```

### 12.8.6 Deftemplate Slot Existence

The deftemplate-slot-existp function returns the symbol TRUE if the specified slot is present in
the specified deftemplate; otherwise, it returns the symbol FALSE.

Syntax

```
(deftemplate-slot-existp <deftemplate-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
(slot age))
CLIPS> (deftemplate-slot-existp person name)
TRUE
CLIPS> (deftemplate-slot-existp person gender)
FALSE
CLIPS>
```

### 12.8.7 Testing whether a Deftemplate Slot is a Multifield Slot

The deftemplate-slot-multip function returns the symbol TRUE if the specified slot in the
specified deftemplate is a multifield slot; otherwise, it returns the symbol FALSE. An error is
generated if the specified deftemplate or slot does not exist.

Syntax

```
(deftemplate-slot-multip <deftemplate-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
(slot age)
(multislot hobbies))
CLIPS> (deftemplate-slot-multip person name)
FALSE
CLIPS> (deftemplate-slot-multip person hobbies)
TRUE
CLIPS>
```

```
228 Section 12: Actions and Functions
```

### 12.8.8 Determining the Slot Names Associated with a Deftemplate

The deftemplate-slot-names function returns the slot names associated with the deftemplate in a
multifield value. The symbol implied is returned for an implied deftemplate (which has a single
implied multifield slot). The symbol FALSE is returned if the specified deftemplate does not exist.

Syntax

```
(deftemplate-slot-names <deftemplate-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
(slot age)
(multislot hobbies))
CLIPS> (deftemplate-slot-names person)
(name age hobbies)
CLIPS>
```

### 12.8.9 Getting the Numeric Range for a Deftemplate Slot

The deftemplate-slot-range function groups the minimum and maximum numeric ranges allowed
for a slot into a multifield variable. A minimum value of infinity is indicated by the symbol -oo
(the minus character followed by two lowercase ‘o’ characters—not zeroes). A maximum value of
infinity is indicated by the symbol +oo (the plus character followed by two lowercase ‘o’
characters). The symbol FALSE is returned for slots in which numeric values are not allowed. A
multifield of length zero is returned if an error occurs.

Syntax

```
(deftemplate-slot-range <deftemplate-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name (type STRING))
(slot age (type INTEGER) (range 0 120))
(slot net-worth (type FLOAT)))
CLIPS> (deftemplate-slot-range person name)
FALSE
CLIPS> (deftemplate-slot-range person age)
(0 120)
CLIPS> (deftemplate-slot-range person net-worth)
(-oo +oo)
```

```
CLIPS Basic Programming Guide 229
```

```
CLIPS>
```

### 12.8.10 Testing whether a Deftemplate Slot is a Single-Field Slot

The deftemplate-slot-singlep function returns the symbol TRUE if the specified slot in the
specified deftemplate is a single-field slot; otherwise, it returns the symbol FALSE. An error is
generated if the specified deftemplate or slot does not exist.

Syntax

```
(deftemplate-slot-singlep <deftemplate-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
(slot age)
(multislot hobbies))
CLIPS> (deftemplate-slot-singlep person name)
TRUE
CLIPS> (deftemplate-slot-singlep person hobbies)
FALSE
CLIPS>
```

### 12.8.11 Getting the Primitive Types for a Deftemplate Slot

The deftemplate-slot-types function groups the names of the primitive types allowed for a
deftemplate slot into a multifield variable. A multifield of length zero is returned if an error occurs.

Syntax

```
(deftemplate-slot-types <deftemplate-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name (type STRING))
(slot age (type INTEGER) (range 0 120))
(slot net-worth (type FLOAT))
(multislot tags (type LEXEME NUMBER)))
CLIPS> (deftemplate-slot-types person age)
(INTEGER)
CLIPS> (deftemplate-slot-types person tags)
(FLOAT INTEGER SYMBOL STRING)
CLIPS>
```

```
230 Section 12: Actions and Functions
```

### 12.8.12 Getting the List of Deftemplates

The get-deftemplate-list function returns a multifield value containing the names of all
deftemplate constructs facts visible to the module specified by <module-name> or to the current
module if none is specified. If the symbol \* is specified as the module name, then all deftemplates
are returned.

Syntax

```
(get-deftemplate-list [<module-name>])
```

Example

```
CLIPS> (clear)
CLIPS> (deftemplate person)
CLIPS> (deftemplate order)
CLIPS> (get-deftemplate-list)
(person order)
CLIPS>
```

## 12.9 Fact Functions

The following actions are used for assert, retracting, and modifying facts.

### 12.9.1 Creating New Facts

The assert function creates new facts and adds them to the fact-list. Multiple facts may be asserted
with each call. If the facts item is being watched as a result of the watch command, then an
informational message will be printed each time a fact is asserted.

Syntax

```
(assert <RHS-pattern>+)
```

Missing slots in a template fact being asserted are assigned their default value. If an identical copy
of the fact already exists in the fact-list, the fact will not be added (however, this behavior can be
changed using the set-fact-duplication command). Note that in addition to constants, expressions
can be placed within a fact to be asserted. The first field of a fact must be a symbol. The value
returned of the assert function is the fact-address of the last fact asserted. If an identical copy of
the last fact already exists in the fact-list, then the fact-address of the existing fact is returned. If
the assertion of the last fact causes an error, then the symbol FALSE is returned.

Example

```
CLIPS> (clear)
CLIPS> (assert (color red))
```

```
CLIPS Basic Programming Guide 231
```

```
<Fact- 1 >
CLIPS> (assert (color blue) (value (+ 3 4)))
<Fact- 3 >
CLIPS> (assert (color red))
FALSE
CLIPS> (deftemplate status (slot temp) (slot pressure))
CLIPS> (assert (status (temp high)
(pressure low)))
<Fact- 4 >
CLIPS> (facts)
f-1 (color red)
f-2 (color blue)
f-3 (value 7)
f-4 (status (temp high) (pressure low))
For a total of 4 facts.
CLIPS>
```

### 12.9.2 Removing Facts from the Fact-list

The retract function removes facts from the fact-list. Multiple facts may be retracted with a single
retract call. The retraction of a fact also removes all rules that depended upon that fact for activation
from the agenda. Retraction of a fact may also cause the retraction of other facts which receive
logical support from the retracted fact. If the facts item is being watched as a result of the watch
command, then an informational message will be printed each time a fact is retracted.

Syntax

```
(retract <retract-specifier>+ | *)
```

```
<retract-specifier> ::= <fact-specifier> | <integer-expression>
```

The <retract-specifier> term includes variables bound on the LHS to fact-addresses, the fact-index
of the desired fact (e.g. 3 for the fact labeled f-3), or an expression which evaluates to a
retract-specifier. If the symbol \* is used as an argument, all facts will be retracted. This function
has no return value.

Example

```
CLIPS> (clear)
CLIPS>
(defrule purchased
?gl <- (grocery-list $?b ?item $?e)
?p <- (purchased ?item)
=>
(retract ?gl ?p)
(assert (grocery-list ?b ?e)))
CLIPS> (assert (grocery-list milk eggs cheese))
<Fact-1>
CLIPS> (assert (purchased milk) (purchased cheese))
```

```
232 Section 12: Actions and Functions
```

```
<Fact-3>
CLIPS> (watch rules)
CLIPS> (watch facts)
CLIPS> (run)
FIRE 1 purchased: f-1,f- 3
<== f-1 (grocery-list milk eggs cheese)
<== f-3 (purchased cheese)
==> f-4 (grocery-list milk eggs)
FIRE 2 purchased: f-4,f- 2
<== f-4 (grocery-list milk eggs)
<== f-2 (purchased milk)
==> f-5 (grocery-list eggs)
CLIPS> (facts)
f-5 (grocery-list eggs)
For a total of 1 fact.
CLIPS> (unwatch all)
CLIPS>
```

### 12.9.3 Modifying Template Facts

The modify function modifies the slot values of an existing template fact. Only one fact may be
modified with a single modify call. The modification of a fact is equivalent to retracting the present
fact and asserting the modified fact. Therefore, any facts receiving logical support from a template
fact are retracted (assuming no other support) when the template fact is modified and the new
template fact loses any logical support that it previously had.

Syntax

```
(modify <fact-specifier> <RHS-slot>*)
```

The <fact-specifier> term includes variables bound on the LHS to fact-addresses, the fact-index
of the desired fact (e.g. 3 for the fact labeled f-3), or an expression which evaluates to a
fact-specifier. Static deftemplate checking is not performed when a fact-index is used as the
<fact-specifier> since the deftemplate being referenced is unknown until the action is executed.
The value returned by this function is the fact-address of the newly modified fact. If an identical
copy of the newly modified fact already exists in the fact-list, the fact-address of the existing copy
is returned; otherwise the fact-address and fact-index of a modified fact is preserved. If the
assertion of the newly modified fact causes an error, the symbol FALSE is returned. If all slot
changes specified in the modify command match the current values of the fact to be modified, no
action is taken.

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate valve
(slot id)
(slot state))
```

```
CLIPS Basic Programming Guide 233
```

```
CLIPS>
(deftemplate set
(slot id)
(slot state))
CLIPS>
(defrule change-valve-status
?f1 <- (valve (id ?v) (state ?state))
?f2 <- (set (id ?v) (state ?new-state))
=>
(retract ?f2)
(modify ?f1 (state ?new-state)))
CLIPS> (assert (valve (id 1) (state open)))
<Fact-1>
CLIPS> (assert (set (id 1) (state closed)))
<Fact-2>
CLIPS> (watch facts)
CLIPS> (run)
<== f-2 (set (id 1) (state closed))
<== f-1 (valve ... (state open))
==> f-1 (valve ... (state closed))
CLIPS> (unwatch facts)
CLIPS>
```

### 12.9.4 Duplicating Template Facts

The duplicate function creates a new template fact from the slot values of an existing template
fact. The new fact is created by assigning the slot values specified in the duplicate call and then
copying the remaining slot values from the existing fact. Only one fact may be duplicated with a
single duplicate statement. The duplicate function is similar to the modify function except the fact
being duplicated is not retracted.

Syntax

```
(duplicate <fact-specifier> <RHS-slot>*)
```

The <fact-specifier> term includes variables bound on the LHS to fact-addresses, the fact-index
of the desired fact (e.g. 3 for the fact labeled f-3), or an expression which evaluates to a
fact-specifier. Static deftemplate checking is not performed when a fact-index is used as the
<fact-specifier> since the deftemplate being referenced is usually ambiguous. The value returned
by this function is the fact-address of the newly duplicated fact. If an identical copy of the newly
duplicated fact already exists in the fact-list, the fact-address of the existing copy is returned. If
the assertion of the newly duplicated fact causes an error, then the symbol FALSE is returned.

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate order
```

```
234 Section 12: Actions and Functions
```

```
(slot id)
(slot item)
(slot quantity))
CLIPS>
(defrule clone-order
?c <- (clone ?id ?new-id)
?o <- (order (id ?id))
=>
(retract ?c)
(duplicate ?o (id ?new-id)))
CLIPS> (assert (order (id o1) (item #6732938) (quantity 2)))
<Fact-1>
CLIPS> (assert (clone o1 o2))
<Fact-2>
CLIPS> (watch facts)
CLIPS> (run)
<== f-2 (clone o1 o2)
==> f-3 (order (id o2) (item #6732938) (quantity 2))
CLIPS> (unwatch facts)
CLIPS>
```

### 12.9.5 Asserting a String

The assert-string function is similar to the assert function in that it creates a new fact and adds it
to the fact-list. However, assert-string takes a single string representing a fact (expressed in either
ordered or deftemplate format) and asserts it. Only one fact may be asserted with each
assert-string statement.

Syntax

```
(assert-string <string-expression>)
```

If an identical copy of the fact already exists in the fact-list, the fact will not be added (however,
this behavior can be changed using the set-fact-duplication command). Fields within the fact may
contain a string by escaping the quote character with a backslash. Note that this function takes a
string and turns it into fields. If the fields within that string are going to contain special characters
(such as a backslash), they need to be escaped twice (because you are literally embedding a string
within a string and the backslash mechanism ends up being applied twice). Global variables and
expressions can be contained within the string. The value returned by this function is the
fact-address of the newly created fact. If an identical copy of the newly created fact already exists
in the fact-list, the fact-address of the existing copy is returned. If the assertion of the newly created
fact causes an error, then the symbol FALSE is returned.

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
```

```
CLIPS Basic Programming Guide 235
```

```
(slot age))
CLIPS> (assert-string "(grocery-list milk eggs cheese)")
<Fact-1>
CLIPS> (assert-string "(fees-paid \"N\\\\A\")")
<Fact-2>
CLIPS> (assert-string "(person (name \"Jack Farmer\") (age 23))")
<Fact-3>
CLIPS> (facts)
f-1 (grocery-list milk eggs cheese)
f-2 (fees-paid "N\A")
f-3 (person (name "Jack Farmer") (age 23))
For a total of 3 facts.
CLIPS>
```

### 12.9.6 Getting the Fact-Index of a Fact-address

The fact-index function returns the fact-index (an integer) of a fact-address.

Syntax

```
(fact-index <fact-address>)
```

Example

```
CLIPS> (clear)
CLIPS> (bind ?f (assert (grocery-list milk eggs cheese)))
<Fact-1>
CLIPS> (fact-index ?f)
1
CLIPS>
```

### 12.9.7 Determining If a Fact Exists

The fact-existp function returns the symbol TRUE if the fact specified by its fact-index or fact-
address argument exists; otherwise, the symbol FALSE is returned.

Syntax

```
(fact-existp <fact-address-or-index>)
```

Example

```
CLIPS> (clear)
CLIPS> (assert (grocery-list milk eggs cheese))
<Fact-1>
CLIPS> (fact-existp 1)
TRUE
CLIPS> (retract 1)
CLIPS> (fact-existp 1)
```

```
236 Section 12: Actions and Functions
```

```
FALSE
CLIPS>
```

### 12.9.8 Determining the Deftemplate (Relation) Name Associated with a Fact

The fact-relation function returns the deftemplate (relation) name associated with the fact. The
symbol FALSE is returned if the specified fact does not exist.

Syntax

```
(fact-relation <fact-address-or-index>)
```

Example

```
CLIPS> (clear)
CLIPS> (assert (grocery-list milk eggs cheese))
<Fact-1>
CLIPS> (fact-relation 1)
grocery-list
CLIPS>
```

### 12.9.9 Determining the Slot Names Associated with a Fact............................................

The fact-slot-names function returns a multifield value containing the slot names associated with
a fact. The symbol implied is returned for an ordered fact (which has a single implied multifield
slot). The symbol FALSE is returned if the specified fact does not exist.

Syntax

```
(fact-slot-names <fact-address-or-index>)
```

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
(slot age)
(multislot hobbies))
CLIPS> (assert (grocery-list milk eggs cheese))
<Fact-1>
CLIPS> (assert (person (name "Jack Smith") (age 23) (hobbies movies golf)))
<Fact-2>
CLIPS> (fact-slot-names 1)
(implied)
CLIPS> (fact-slot-names 2)
(name age hobbies)
CLIPS>
```

```
CLIPS Basic Programming Guide 237
```

### 12.9.10 Retrieving the Slot Value of a Fact

The fact-slot-value function returns the value of the specified slot from the specified fact. The
symbol implied should be used as the slot name for the implied multifield slot of an ordered fact.
The symbol FALSE is returned if the slot name argument is invalid or the specified fact does not
exist.

Syntax

```
(fact-slot-value <fact-address-or-index> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(slot name)
(slot age)
(multislot hobbies))
CLIPS> (assert (grocery-list milk eggs cheese))
<Fact-1>
CLIPS> (assert (person (name "Jack Smith") (age 23) (hobbies movies golf)))
<Fact-2>
CLIPS> (fact-slot-value 1 implied)
(milk eggs cheese)
CLIPS> (fact-slot-value 2 name)
"Jack Smith"
CLIPS> (fact-slot-value 2 hobbies)
(movies golf)
CLIPS>
```

### 12.9.11 Retrieving the Fact-List

The get-fact-list function returns a multifield containing the list of facts visible to the module
specified by <module-name> or to the current module if none is specified. If the symbol \* is
specified as the module name, then all facts are returned.

Syntax

```
(get-fact-list [<module-name>])
```

Example

```
CLIPS> (clear)
CLIPS> (defmodule PEOPLE)
CLIPS>
(deftemplate person
(slot name)
(slot credit))
```

```
238 Section 12: Actions and Functions
```

```
CLIPS> (assert (person (name "Jack Smith") (credit 100.0)))
<Fact-1>
CLIPS> (defmodule ORDERS)
CLIPS>
(deftemplate order
(slot item)
(slot quantity)
(slot customer))
CLIPS> (assert (order (item #7362383) (quantity 2) (customer "Jack Smith")))
<Fact-2>
CLIPS> (get-fact-list)
(<Fact-2>)
CLIPS> (get-fact-list PEOPLE)
(<Fact-1>)
CLIPS> (get-fact-list *)
(<Fact-1> <Fact-2>)
CLIPS>
```

### 12.9.12 Fact-set Queries and Distributed Actions

CLIPS provides a query system for finding and performing actions on sets of facts that satisfy
queries. The fact query system provides the six functions shown in the following table.

```
Function Purpose
```

```
any-factp Determines if one or more factsatisfy a query - sets
```

```
find-fact Returns the first factquery - set that satisfies a
```

```
find-all-facts Groups and returns all factsatisfy a query - sets which
```

```
do-for-fact Performs an action for the first factwhich satisfies a query - set
```

```
do-for-all-facts Performs an action for every factwhich satisfies a query as they are found-set
```

```
delayed-do-for-all-facts Groups all factand then iterates an action over this group-sets which satisfy a query
```

The following diagram shows a fact-set query function call with key components labeled. The
various components will be discussed later in this section.

```
CLIPS Basic Programming Guide 239
```

The examples in this section assume that the following commands have already been entered.

```
CLIPS> (clear)
CLIPS>
(deftemplate girl
(slot name)
(slot sex (default female))
(slot age (default 4)))
CLIPS>
(deftemplate woman
(slot name)
(slot sex (default female))
(slot age (default 25)))
CLIPS>
(deftemplate boy
(slot name)
(slot sex (default male))
(slot age (default 4)))
CLIPS>
(deftemplate man
(slot name)
(slot sex (default male))
(slot age (default 25)))
CLIPS>
(deffacts PEOPLE
(man (name Man-1) (age 18))
(man (name Man-2) (age 60))
(woman (name Woman-1) (age 18))
(woman (name Woman-2) (age 60))
(woman (name Woman-3))
(boy (name Boy-1) (age 8))
(boy (name Boy-2))
(boy (name Boy-3))
(boy (name Boy-4))
(girl (name Girl-1) (age 8))
(girl (name Girl-2)))
CLIPS> (reset)
CLIPS> (facts)
f-1 (man (name Man-1) (sex male) (age 18))
f-2 (man (name Man-2) (sex male) (age 60))
f-3 (woman (name Woman-1) (sex female) (age 18))
```

```
240 Section 12: Actions and Functions
```

```
f-4 (woman (name Woman-2) (sex female) (age 60))
f-5 (woman (name Woman-3) (sex female) (age 25))
f-6 (boy (name Boy-1) (sex male) (age 8))
f-7 (boy (name Boy-2) (sex male) (age 4))
f-8 (boy (name Boy-3) (sex male) (age 4))
f-9 (boy (name Boy-4) (sex male) (age 4))
f-10 (girl (name Girl-1) (sex female) (age 8))
f-11 (girl (name Girl-2) (sex female) (age 4))
For a total of 1 1 facts.
CLIPS>
```

12.9.12.1 Fact-set Definition

A fact-set is an ordered collection of facts. Each fact-set member is a member of a set of
deftemplates, called template restrictions, specified in the function call. The template restrictions
can be different for each fact-set member. The query functions use fact-set templates to generate
fact-sets. A fact-set template is a set of fact-set member variables and their associated template
restrictions. Fact-set member variables reference the corresponding members in each fact-set
which matches a template. Variables may be used to specify the deftemplates for the fact-set
template, but if the constant names of the deftemplates are specified, the deftemplates must already
be defined. Module specifiers may be included with the deftemplate names; the deftemplates need
not be in scope of the current module.

Syntax

```
<fact-set-template>
::= (<fact-set-member-template>+)
<fact-set-member-template>
::= (<fact-set-member-variable> <deftemplate-restrictions>)
<fact-set-member-variable> ::= <single-field-variable>
<deftemplate-restrictions> ::= <deftemplate-name-expression>+
```

Example

```
One fact-set template might be the ordered pairs of boys or men and girls or women.
```

```
((?man-or-boy boy man) (?woman-or-girl girl woman))
```

```
Fact-set member variables (e.g. ?man-or-boy) are bound to fact-addresses.
```

12.9.12.2 Fact-set Determination

CLIPS uses straightforward permutations to generate fact-sets that match a fact-set template from
the actual facts in the system. The rules are as follows:

```
1) When there is more than one member in a fact-set template, vary the rightmost members first.
```

```
CLIPS Basic Programming Guide 241
```

```
2) When there is more than one deftemplate that a fact-set member can be, iterate through the
deftemplates from left to right.
```

```
3) Examine facts of a deftemplate in the order that they were defined.
```

Example

```
For the fact-set template given in section 12.9.12.1, thirty fact-sets would be generated in the
following order:
```

1. <Fact-6> <Fact-10>
2. <Fact-6> <Fact-11>
3. <Fact-6> <Fact-3>
4. <Fact-6> <Fact-4>
5. <Fact-6> <Fact-5>
6. <Fact-7> <Fact-10>
7. <Fact-7> <Fact-11>
8. <Fact-7> <Fact-3>
9. <Fact-7> <Fact-4>
10. <Fact-7> <Fact-5>
11. <Fact-8> <Fact-10>
12. <Fact-8> <Fact-11>
    13 <Fact-8> <Fact-3>
13. <Fact-8> <Fact-4>
14. <Fact-8> <Fact-5> 16. <Fact-9> <Fact-10> 17. <Fact-9> <Fact-11> 18. <Fact-9> <Fact-3> 19. <Fact-9> <Fact-4> 20. <Fact-9> <Fact-5> 21. <Fact-1> <Fact-10> 22. <Fact-1> <Fact-11> 23. <Fact-1> <Fact-3> 24. <Fact-1> <Fact-4> 25. <Fact-1> <Fact-5> 26. <Fact-2> <Fact-10> 27. <Fact-2> <Fact-11> 28. <Fact-2> <Fact-3> 29. <Fact-2> <Fact-4> 30. <Fact-2> <Fact-5>

12.9.12.3 Query Definition

A query is a boolean expression applied to a fact-set to determine if the fact-set meets further
restrictions. If the return value of this expression for an fact-set is not the symbol FALSE, the
fact-set is said to satisfy the query.

Syntax

```
<query> ::= <boolean-expression>
```

Example

```
Continuing the previous example, one query might be that the two facts in an ordered pair
have the same age.
```

```
(= (fact-slot-value ?man-or-boy age) (fact-slot-value ?woman-or-girl age))
```

Within a query, slots of fact-set members can be directly read with a shorthand notation similar to
that used by instances in message-handlers.

```
242 Section 12: Actions and Functions
```

Syntax

```
<fact-set-member-variable>:<slot-name>
```

Example

```
The previous example could be rewritten as:
```

```
(= ?man-or-boy:age ?woman-or-girl:age)
```

Since only fact-sets which satisfy a query are of interest, and the query is evaluated for all possible
fact-sets, the query should not have any side-effects.

12.9.12.4 Distributed Action Definition

A distributed action is a user-defined expression evaluated for each fact-set which satisfies a
query.

Action Syntax

```
<action> ::= <expression>
```

Example

```
Continuing the previous example, one distributed action might be to simply print out the
ordered pair to the screen.
```

```
(println "(" ?man-or-boy:name "," ?woman-or-girl:name ")")
```

12.9.12.5 Scope in Fact-set Query Functions

Fact-set member variables are only in scope within the fact-set query function. Attempting to use
fact-set member variables in an outer scope will generate an error. If a variable from an outer scope
is not masked by a fact-set member variable, then that variable may be referenced within the query
and action. In addition, rebinding variables within a fact-set function action is allowed. However,
attempts to rebind fact-set member variables will generate errors. Binding variables is not allowed
within a query. Fact-set query functions can be nested.

Example 1

```
CLIPS>
(deffunction count-facts (?template)
(bind ?count 0)
(do-for-all-facts ((?fct ?template)) TRUE
(bind ?count (+ ?count 1)))
?count)
```

```
CLIPS Basic Programming Guide 243
```

```
CLIPS>
(deffunction count-facts-2 (?template)
(length (find-all-facts ((?fct ?template)) TRUE)))
CLIPS> (count-facts woman)
3
CLIPS> (count-facts-2 boy)
4
CLIPS>
```

Example 2

```
(deffunction last-fact (?template)
(any-factp ((?fct ?template)) TRUE)
?fct)
```

```
[PRCCODE3] Undefined variable ?fct referenced in deffunction.
```

```
ERROR:
(deffunction ORDERS::last-fact
(?template)
(any-factp ((?fct ?template))
TRUE)
?fct
)
CLIPS>
```

12.9.12.6 Errors during Fact-set Query Functions

If an error occurs during an fact-set query function, the function will be immediately terminated
and the return value will be the symbol FALSE.

12.9.12.7 Halting and Returning Values from Query Functions

The break and return functions are valid inside the action of the fact-set query functions
do-for-fact, do-for-all-facts, and delayed-do-for-all-facts. The return function is only valid if it
is applicable in the outer scope, whereas the break function halts the query.

12.9.12.8 Fact-set Query Functions

The fact query system in CLIPS provides six functions. For a given set of facts, all six query
functions will iterate over these facts in the same order. However, if a particular fact is retracted
and reasserted, the iteration order will change.

```
244 Section 12: Actions and Functions
```

12.9.12.8.1 Testing if Any Fact-set Satisfies a Query

The any-factp function applies a query to each fact-set which matches the template. If a fact-set
satisfies the query, then the function is immediately terminated, and the return value is the symbol
TRUE; otherwise, the symbol FALSE is returned.

Syntax

```
(any-factp <fact-set-template> <query>)
```

Example

```
Are there any men over age 30?
```

```
CLIPS> (any-factp ((?man man)) (> ?man:age 30))
TRUE
CLIPS>
```

12.9.12.8.2 Determining the First Fact-set Satisfying a Query

The find-fact function applies a query to each fact-set which matches the template. If a fact-set
satisfies the query, then the function is immediately terminated, and a multifield value containing
the fact-set is returned. Otherwise, the return value is a zero-length multifield value. Each field of
the multifield value is a fact-address representing a fact-set member.

Syntax

```
(find-fact <fact-set-template> <query>)
```

Example

```
Find the first pair of a man and a woman who have the same age.
```

```
CLIPS>
(find-fact((?m man) (?w woman)) (= ?m:age ?w:age))
(<Fact-1> <Fact-3>)
CLIPS>
```

12.9.12.8.3 Determining All Fact-sets Satisfying a Query

The find-all-facts function applies a query to each fact-set which matches the template. Each
fact-set which satisfies the query is stored in a multifield value. This multifield value is returned
when the query has been applied to all possible fact-sets. If there are n facts in each fact-set, and
m fact-sets satisfied the query, then the length of the returned multifield value will be n \* m. The
first n fields correspond to the first fact-set, and so on. Each field of the multifield value is an
fact-address representing a fact-set member.

```
CLIPS Basic Programming Guide 245
```

Syntax

```
(find-all-facts <fact-set-template> <query>)
```

Example

```
Find all pairs of a man and a woman who have the same age.
```

```
CLIPS>
(find-all-facts ((?m man) (?w woman)) (= ?m:age ?w:age))
(<Fact-1> <Fact-3> <Fact-2> <Fact-4>)
CLIPS>
```

12.9.12.8.4 Executing an Action for the First Fact-set Satisfying a Query

The do-for-fact function applies a query to each fact-set which matches the template. If a fact-set
satisfies the query, the specified action is executed, and the function is immediately terminated.
The return value is the evaluation of the action. If no fact-set satisfied the query, then the return
value is the symbol FALSE.

Syntax

```
(do-for-fact <fact-set-template> <query> <action>*)
```

Example

```
Print out the first triplet of different people that have the same age. The calls to neq in the
query eliminate the permutations where two or more members of the instance-set are identical.
```

```
CLIPS>
(do-for-fact ((?p1 girl boy woman man)
(?p2 girl boy woman man)
(?p3 girl boy woman man))
(and (= ?p1:age ?p2:age ?p3:age)
(neq ?p1 ?p2)
(neq ?p1 ?p3)
(neq ?p2 ?p3))
(println ?p1:name " " ?p2:name " " ?p3:name))
Girl-2 Boy-2 Boy- 3
CLIPS>
```

12.9.12.8.5 Executing an Action for All Fact-sets Satisfying a Query

The do-for-all-facts function applies a query to each fact-set which matches the template. If a
fact-set satisfies the query, the specified action is executed. The return value is the evaluation of

```
246 Section 12: Actions and Functions
```

the action for the last fact-set which satisfied the query. If no fact-set satisfied the query, then the
return value is the symbol FALSE.

Syntax

```
(do-for-all-facts <fact-set-template> <query> <action>*)
```

Example

```
Print out all triplets of different people that have the same age. The calls to str-compare limit
the fact-sets which satisfy the query to combinations instead of permutations. Without these
restrictions, two fact-sets which differed only in the order of their members would both satisfy
the query.
```

```
CLIPS>
(do-for-all-facts ((?p1 girl boy woman man)
(?p2 girl boy woman man)
(?p3 girl boy woman man))
(and (= ?p1:age ?p2:age ?p3:age)
(> (str-compare ?p1:name ?p2:name) 0)
(> (str-compare ?p2:name ?p3:name) 0))
(println ?p1:name " " ?p2:name " " ?p3:name))
Girl-2 Boy-3 Boy- 2
Girl-2 Boy-4 Boy- 2
Girl-2 Boy-4 Boy- 3
Boy-4 Boy-3 Boy- 2
CLIPS>
```

12.9.12.8.6 Executing a Delayed Action for All Fact-sets Satisfying a Query

The delayed-do-for-all-facts function is similar to the do-for-all-facts function except that it
groups all fact-sets which satisfy the query into an intermediary multifield value. If there are no
fact-sets which satisfy the query, then the function returns the symbol FALSE. Otherwise, the
specified action is executed for each fact-set in the multifield value, and the return value is the
evaluation of the action for the last fact-set to satisfy the query. The intermediary multifield value
is discarded. This function should be used in lieu of do-for-all-facts when the action applied to
one fact-set would change the result of the query for another fact-set (unless that is the desired
effect).

Syntax

```
(delayed-do-for-all-facts <fact-set-template>
<query> <action>*)
```

```
CLIPS Basic Programming Guide 247
```

Example

```
Delete all boys with the greatest age. The test in this case is another query function which
determines if there are any older boys than the one currently being examined. The action needs
to be delayed until all boys have been processed, or the greatest age will decrease as the older
boys are deleted.
```

```
CLIPS> (watch facts)
CLIPS>
(delayed-do-for-all-facts ((?b1 boy))
(not (any-factp ((?b2 boy)) (> ?b2:age ?b1:age)))
(retract ?b1))
<== f-6 (boy (name Boy-1) (sex male) (age 8))
CLIPS> (unwatch facts)
CLIPS> (reset)
CLIPS> (watch facts)
CLIPS>
(do-for-all-facts ((?b1 boy))
(not (any-factp ((?b2 boy)) (> ?b2:age ?b1:age)))
(retract ?b1))
<== f- 6 (boy (name Boy-1) (sex male) (age 8))
<== f-7 (boy (name Boy-2) (sex male) (age 4))
<== f-8 (boy (name Boy-3) (sex male) (age 4))
<== f-9 (boy (name Boy-4) (sex male) (age 4))
CLIPS> (unwatch facts)
CLIPS>
```

## 12.10 Deffacts Functions

The following functions provide ancillary capabilities for the deffacts construct.

### 12.10.1 Getting the List of Deffacts.................................................................................

The get-deffacts-list function returns a multifield value containing the names of all deffacts
constructs visible to the module specified by <module-name> or to the current module if none is
specified. If the symbol \* is specified as the module name, then all deffacts are returned.

Syntax

```
(get-deffacts-list [<module-name>])
```

Example

```
CLIPS> (clear)
CLIPS> (get-deffacts-list)
()
CLIPS>
(deffacts initial
```

```
248 Section 12: Actions and Functions
```

```
(grocery-list milk eggs cheese)
(item milk)
(item eggs)
(item cheese))
CLIPS> (get-deffacts-list)
(initial)
CLIPS>
```

### 12.10.2 Determining the Module in which a Deffacts is Defined

The deffacts-module function returns the module in which the specified deffacts name is defined.

Syntax

```
(deffacts-module <deffacts-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(deffacts initial
(grocery-list milk eggs cheese)
(item milk)
(item eggs)
(item cheese))
CLIPS> (deffacts-module initial)
MAIN
CLIPS>
```

## 12.11 Defrule Functions.........................................................................................................

The following functions provide ancillary capabilities for the defrule construct.

### 12.11.1 Getting the List of Defrules

The get-defrule-list function returns a multifield value containing the names of all defrule
constructs visible to the module specified by <module-name> or to the current module if none is
specified. If the symbol \* is specified as the module name, then all defrules are returned.

Syntax

```
(get-defrule-list)
```

### 12.11.2 Determining the Module in which a Defrule is Defined.....................................

The defrule-module function returns the module in which the specified defrule name is defined.

```
CLIPS Basic Programming Guide 249
```

Syntax

```
(defrule-module <defrule-name>)
```

## 12.12 Agenda Functions

The following functions provide ancillary capabilities for manipulating the agenda.

### 12.12.1 Getting the Current Focus

The get-focus function returns the module name of the current focus. If the focus stack is empty,
then the symbol FALSE is returned.

Syntax

```
(get-focus)
```

Example

```
CLIPS> (clear)
CLIPS> (get-focus)
MAIN
CLIPS> (defmodule COLLECT)
CLIPS> (defmodule PROCESS)
CLIPS> (focus COLLECT PROCESS)
TRUE
CLIPS> (get-focus)
COLLECT
CLIPS>
```

### 12.12.2 Getting the Focus Stack

The get-focus-stack function returns a multifield value containing all of the module names in the
focus stack. A multifield value of length zero is returned if the focus stack is empty.

Syntax

```
(get-focus-stack)
```

Example

```
CLIPS> (clear)
CLIPS> (get-focus-stack)
(MAIN)
CLIPS> (run)
CLIPS> (get-focus-stack)
()
```

```
250 Section 12: Actions and Functions
```

```
CLIPS> (defmodule COLLECT)
CLIPS> (defmodule PROCESS)
CLIPS> (focus COLLECT PROCESS)
TRUE
CLIPS> (get-focus-stack)
(COLLECT PROCESS)
CLIPS>
```

### 12.12.3 Removing the Current Focus from the Focus Stack

The pop-focus function removes the current focus from the focus stack and returns the module
name of the current focus. If the focus stack is empty, then the symbol FALSE is returned.

Syntax

```
(pop-focus)
```

Example

```
CLIPS> (clear)
CLIPS> (list-focus-stack)
MAIN
CLIPS> (pop-focus)
MAIN
CLIPS> (list-focus-stack)
CLIPS> (defmodule COLLECT)
CLIPS> (defmodule PROCESS)
CLIPS> (focus COLLECT PROCESS)
TRUE
CLIPS> (list-focus-stack)
COLLECT
PROCESS
CLIPS> (pop-focus)
COLLECT
CLIPS> (list-focus-stack)
PROCESS
CLIPS>
```

## 12.13 Defglobal Functions

The following functions provide ancillary capabilities for the defglobal construct.

12.13.1 Getting the List of Defglobals

The get-defglobal-list function returns a multifield value containing the names of all global
variables visible to the module specified by <module-name> or to the current module if none is
specified. If the symbol \* is specified as the module name, then all globals are returned.

```
CLIPS Basic Programming Guide 251
```

Syntax

```
(get-defglobal-list [<module-name>])
```

### 12.13.2 Determining the Module in which a Defglobal is Defined

The defglobal-module function returns the module in which the specified defglobal name is
defined.

Syntax

```
(defglobal-module <defglobal-name>)
```

## 12.14 Deffunction Functions

The following functions provide ancillary capabilities for the deffunction construct.

### 12.14.1 Getting the List of Deffunctions

The get-deffunction-list function returns a multifield value containing the names of all
deffunction constructs visible to the module specified by <module-name> or to the current module
if none is specified. If the symbol \* is specified as the module name, then all deffunctions are
returned.

Syntax

```
(get-deffunction-list [<module-name>])
```

### 12.14.2 Determining the Module in which a Deffunction is Defined

The deffunction-module function returns the module in which the specified deffunction name is
defined.

Syntax

```
(deffunction-module <deffunction-name>)
```

## 12.15 Generic Function Functions

The following functions provide ancillary capabilities for generic function methods.

```
252 Section 12: Actions and Functions
```

### 12.15.1 Getting the List of Defgenerics

The get-defgeneric-list function returns a multifield value containing the names of all defgeneric
constructs that are currently defined.

Syntax

```
(get-defgeneric-list)
```

### 12.15.2 Determining the Module in which a Generic Function is Defined

The defgeneric-module function returns the module in which the specified defgeneric name is
defined.

Syntax

```
(defgeneric-module <defgeneric-name>)
```

### 12.15.3 Getting the List of Defmethods...........................................................................

The get-defmethod-list function returns a multifield value containing method name/indices pairs
for all defmethod constructs that are currently defined. The optional <generic-function-name>
parameter restricts the methods return value to only those of the specified generic function.

Syntax

```
(get-defmethod-list [<generic-function-name>])
```

Example

```
CLIPS> (clear)
CLIPS> (get-defmethod-list)
()
CLIPS> (defmethod add ((?x MULTIFIELD) (?y MULTIFIELD)) (create$ ?x ?y))
CLIPS> (defmethod add ((?x STRING) (?y STRING)) (str-cat ?x ?y))
CLIPS>
(defmethod subtract ((?x MULTIFIELD) (?y MULTIFIELD)) (delete-member$ ?x ?y))
CLIPS> (get-defmethod-list)
(add 1 add 2 subtract 1)
CLIPS> (get-defmethod-list add)
(add 1 add 2)
CLIPS>
```

```
CLIPS Basic Programming Guide 253
```

### 12.15.4 Type Determination

The type function returns a symbol which is the name of the type (or class) of its argument. This
function is equivalent to the class function, but, unlike the class function, it is available even when
COOL is not installed.

Syntax

```
(type <expression>)
```

Example

```
CLIPS> (clear)
CLIPS> (type (+ 2 2))
INTEGER
CLIPS> (defclass CAR (is-a USER))
CLIPS> (make-instance Rolls-Royce of CAR)
[Rolls-Royce]
CLIPS> (type Rolls-Royce)
SYMBOL
CLIPS> (type [Rolls-Royce])
CAR
CLIPS>
```

### 12.15.5 Existence of Shadowed Methods

If called from a method for a generic function, the next-methodp function will return the symbol
TRUE if there is another method shadowed by the current one; otherwise, the function will return
the symbol FALSE.

Syntax

```
(next-methodp)
```

### 12.15.6 Calling Shadowed Methods

If the conditions are such that the next-methodp function would return the symbol TRUE, then
calling the call-next-method function will execute the shadowed method; otherwise, a method
execution error will occur. In the event of an error, the return value of this function is the symbol
FALSE, otherwise it is the return value of the shadowed method. The shadowed method is passed
the same arguments as the calling method.

A method may continue execution after calling call-next-method. In addition, a method may make
multiple calls to call-next-method, and the same shadowed method will be executed each time.

```
254 Section 12: Actions and Functions
```

Syntax

```
(call-next-method)
```

Example

```
CLIPS> (clear)
CLIPS>
(defmethod describe ((?a INTEGER))
(if (next-methodp) then
(bind ?extension (str-cat " " (call-next-method)))
else
(bind ?extension ""))
(str-cat "INTEGER" ?extension))
CLIPS> (describe 3)
"INTEGER"
CLIPS>
(defmethod describe ((?a NUMBER))
"NUMBER")
CLIPS> (describe 3)
"INTEGER NUMBER"
CLIPS> (describe 3.0)
"NUMBER"
CLIPS>
```

### 12.15.7 Calling Shadowed Methods with Overrides

The override-next-method function is similar to call-next-method, except that new arguments
can be provided. This allows one method to act as a wrapper for another and set up a special
environment for the shadowed method. From the set of methods which are more general than the
currently executing one, the most specific method which is applicable to the new arguments is
executed. (In contrast, call-next-method calls the next most specific method which is applicable
to the same arguments as the currently executing one received.) A recursive call to the generic
function itself should be used in lieu of override-next-method if the most specific of all methods
for the generic function which is applicable to the new arguments should be executed.

Syntax

```
(override-next-method <expression>*)
```

Example

```
CLIPS> (clear)
CLIPS>
(defmethod + ((?a INTEGER) (?b INTEGER))
(override-next-method (* ?a 2) (* ?b 3)))
CLIPS> (list-defmethods +)
+ #2 (INTEGER) (INTEGER)
+ #SYS1 (NUMBER) (NUMBER) ($? NUMBER)
For a total of 2 methods.
```

```
CLIPS Basic Programming Guide 255
```

```
CLIPS> (preview-generic + 1 2)
+ #2 (INTEGER) (INTEGER)
+ #SYS1 (NUMBER) (NUMBER) ($? NUMBER)
CLIPS> (watch methods)
CLIPS> (+ 1 2)
MTH >> +:#2 ED:1 (1 2)
MTH >> +:#SYS1 ED:2 (2 6)
MTH << +:#SYS1 ED:2 (2 6)
MTH << +:#2 ED:1 (1 2)
8
CLIPS> (unwatch methods)
CLIPS>
```

### 12.15.8 Calling a Specific Method

The call-specific-method function allows a particular method of a generic function to be called
without regards to method precedence. This allows method precedence to be bypassed when
absolutely necessary. The method must be applicable to the arguments passed. Shadowed methods
can still be called via call-next-method and override-next-method.

Syntax

```
(call-specific-method <generic-function> <method-index>
<expression>*)
```

Example

```
CLIPS> (clear)
CLIPS>
(defmethod + ((?a INTEGER) (?b INTEGER))
(* (- ?a ?b) (- ?b ?a)))
CLIPS> (list-defmethods +)
+ #2 (INTEGER) (INTEGER)
+ #SYS1 (NUMBER) (NUMBER) ($? NUMBER)
For a total of 2 methods.
CLIPS> (preview-generic + 1 2)
+ #2 (INTEGER) (INTEGER)
+ #SYS1 (NUMBER) (NUMBER) ($? NUMBER)
CLIPS> (watch methods)
CLIPS> (+ 1 2)
MTH >> +:#2 ED:1 (1 2)
MTH << +:#2 ED:1 (1 2)
```

- 1
  CLIPS> (call-specific-method + 1 1 2)
  MTH >> +:#SYS1 ED:1 (1 2)
  MTH << +:#SYS1 ED:1 (1 2)
  3
  CLIPS> (unwatch methods)
  CLIPS>

```
256 Section 12: Actions and Functions
```

### 12.15.9 Getting the Restrictions of Defmethods

The get-method-restrictions function returns a multifield value containing information about the
restrictions for the specified method using the following format:

```
<minimum-number-of-arguments>
<maximum-number-of-arguments> (can be -1 for wildcards)
<number-of-restrictions>
<multifield-index-of-first-restriction-info>
.
.
.
<multifield-index-of-nth-restriction-info>
<first-restriction-query> (TRUE or FALSE)
<first-restriction-class-count>
<first-restriction-first-class>
.
.
.
<first-restriction-nth-class>
.
.
.
<mth-restriction-class-count>
<mth-restriction-first-class>
.
.
.
<mth-restriction-nth-class>
```

Syntax

```
(get-method-restrictions <generic-function-name>
<method-index>)
```

Example

```
CLIPS> (clear)
CLIPS> (defmethod example 50 ((?a INTEGER SYMBOL) (?b (= 1 1)) $?c))
CLIPS> (get-method-restrictions example 50)
(2 -1 3 7 11 13 FALSE 2 INTEGER SYMBOL TRUE 0 FALSE 0)
CLIPS>
```

```
CLIPS Basic Programming Guide 257
```

## 12.16 Defclass Functions

### 12.16.1 Getting the List of Defclasses

The get-defclass-list function returns a multifield value containing the names of all defclass
constructs visible to the module specified by <module-name> or to the current module if none is
specified. If the symbol \* is specified as the module name, then all defclasses are returned.

Syntax

```
(get-defclass-list [<module-name>])
```

Example

```
CLIPS> (clear)
CLIPS> (get-defclass-list)
(FLOAT INTEGER SYMBOL STRING MULTIFIELD EXTERNAL-ADDRESS FACT-ADDRESS INSTANCE-
ADDRESS INSTANCE-NAME OBJECT PRIMITIVE NUMBER LEXEME ADDRESS INSTANCE USER)
CLIPS> (defclass ORDER (is-a USER))
CLIPS> (defclass CUSTOMER (is-a USER))
CLIPS> (get-defclass-list)
(FLOAT INTEGER SYMBOL STRING MULTIFIELD EXTERNAL-ADDRESS FACT-ADDRESS INSTANCE-
ADDRESS INSTANCE-NAME OBJECT PRIMITIVE NUMBER LEXEME ADDRESS INSTANCE USER ORDER
CUSTOMER)
CLIPS>
```

### 12.16.2 Determining the Module in which a Defclass is Defined

The defclass-module function returns the module in which the specified defclass name is defined.

Syntax

```
(defclass-module <defclass-name>)
```

### 12.16.3 Determining if a Class Exists

The class-existp function returns the symbol TRUE if the specified class is defined; otherwise, it
returns the symbol FALSE.

Syntax

```
(class-existp <class-name>)
```

```
258 Section 12: Actions and Functions
```

### 12.16.4 Superclass Determination

The superclassp function returns the symbol TRUE if the first class is a superclass of the second
class; otherwise, it returns the symbol FALSE.

Syntax

```
(superclassp <class1-name> <class2-name>)
```

### 12.16.5 Subclass Determination

The subclassp function returns the symbol TRUE if the first class is a subclass of the second class;
otherwise, it returns the symbol FALSE.

Syntax

```
(subclassp <class1-name> <class2-name>)
```

### 12.16.6 Slot Existence......................................................................................................

The slot-existp function returns the symbol TRUE if the specified slot is present in the specified
class; otherwise, it returns the symbol FALSE. If the inherit keyword is specified, then the slot
may be inherited; otherwise it must be directly defined in the specified class.

Syntax

```
(slot-existp <class> <slot> [inherit])
```

### 12.16.7 Testing whether a Slot is Writable

The slot-writablep function returns the symbol TRUE if the specified slot in the specified class
is writable; otherwise, it returns the symbol FALSE. An error is generated if the specified class or
slot does not exist.

Syntax

```
(slot-writablep <class-expression> <slot-name-expression>)
```

### 12.16.8 Testing whether a Slot is Initializable

The slot-initablep function returns the symbol TRUE if the specified slot in the specified class is
initializable; otherwise, it returns the symbol FALSE. An error is generated if the specified class
or slot does not exist.

```
CLIPS Basic Programming Guide 259
```

Syntax

```
(slot-initablep <class-expression> <slot-name-expression>)
```

### 12.16.9 Testing whether a Slot is Public..........................................................................

The slot-publicp function returns the symbol TRUE if the specified slot in the specified class is
public; otherwise, it returns the symbol FALSE. An error is generated if the specified class or slot
does not exist.

Syntax

```
(slot-publicp <class-expression> <slot-name-expression>)
```

### 12.16.10 Testing whether a Slot can be Accessed Directly

The slot-direct-accessp function returns the symbol TRUE if the specified slot in the specified
class can be accessed directly; otherwise, it returns the symbol FALSE. An error is generated if
the specified class or slot does not exist.

Syntax

```
(slot-direct-accessp <class-expression> <slot-name-expression>)
```

### 12.16.11 Message-handler Existence

The message-handler-existp function returns the symbol TRUE if the specified message-handler
is defined (directly only, not by inheritance) for the class; otherwise, it returns the symbol FALSE.

Syntax

```
(message-handler-existp <class-name> <handler-name> [<handler-type>])
```

```
<handler-type> ::= around | before | primary | after
```

If unspecified, the <handler-type> term defaults to the symbol primary.

### 12.16.12 Determining if a Class can have Direct Instances

The class-abstractp function returns the symbol TRUE if the specified class is abstract (i.e. the
class cannot have direct instances); otherwise, it returns the symbol FALSE.

```
260 Section 12: Actions and Functions
```

Syntax

```
(class-abstractp <class-name>)
```

### 12.16.13 Determining if a Class can Satisfy Object Patterns

The class-reactivep function returns the symbol TRUE if the specified class is reactive (i.e.
objects of the class can match object patterns); otherwise it returns the symbol FALSE.

Syntax

```
(class-reactivep <class-name>)
```

### 12.16.14 Getting the List of Superclasses for a Class......................................................

The class-superclasses function returns a multifield value containing the names of the direct
superclasses of the specified class. If the optional argument inherit is specified, indirect
superclasses are also included. A multifield value of length zero is returned if an error occurs.

Syntax

```
(class-superclasses <class-name> [inherit])
```

Example

```
CLIPS> (class-superclasses INTEGER)
(NUMBER)
CLIPS> (class-superclasses INTEGER inherit)
(NUMBER PRIMITIVE OBJECT)
CLIPS>
```

### 12.16.15 Getting the List of Subclasses for a Class

The class-subclasses function returns a multifield value containing the names of the direct
subclasses of the specified class. If the optional argument inherit is specified, indirect subclasses
are also included. A multifield value of length zero is returned if an error occurs.

Syntax

```
(class-subclasses <class-name> [inherit])
```

Example

```
CLIPS> (class-subclasses PRIMITIVE)
(NUMBER LEXEME MULTIFIELD ADDRESS INSTANCE)
CLIPS> (class-subclasses PRIMITIVE inherit)
```

```
CLIPS Basic Programming Guide 261
```

```
(NUMBER INTEGER FLOAT LEXEME SYMBOL STRING MULTIFIELD ADDRESS EXTERNAL-ADDRESS
FACT-ADDRESS INSTANCE-ADDRESS INSTANCE INSTANCE-NAME)
CLIPS>
```

### 12.16.16 Getting the List of Slots for a Class

The class-slots function returns a multifield value containing the names of the explicitly defined
slots of the specified class. If the optional argument inherit is given, inherited slots are also
included. A multifield value of length zero is returned if an error occurs.

Syntax

```
(class-slots <class-name> [inherit])
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass VEHICLE (is-a USER)
(slot wheels)
(slot engine))
CLIPS>
(defclass CAR (is-a VEHICLE)
(slot make)
(slot model))
CLIPS> (class-slots CAR)
(make model)
CLIPS> (class-slots CAR inherit)
(wheels engine make model)
CLIPS>
```

### 12.16.17 Getting the List of Message-Handlers for a Class

The get-defmessage-handler-list function returns a multifield value containing the class names,
message names, and message types of the message-handlers attached directly to the specified class
(implicit slot-accessors are not included). If the optional argument inherit is specified, inherited
message-handlers are also included. A multifield value of length zero is returned if an error occurs.

Syntax

```
(get-defmessage-handler-list <class-name> [inherit])
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass PERSON
(is-a USER)
```

```
262 Section 12: Actions and Functions
```

```
(slot first-name (create-accessor ?NONE))
(slot middle-name (create-accessor ?NONE))
(slot last-name (create-accessor ?NONE)))
CLIPS>
(defmessage-handler PERSON full-name ()
(str-cat ?self:first-name " " ?self:middle-name " " ?self:last-name))
CLIPS> (get-defmessage-handler-list PERSON)
(PERSON full-name primary)
CLIPS> (get-defmessage-handler-list PERSON inherit)
(USER init primary USER delete primary USER create primary USER print primary
USER direct-modify primary USER message-modify primary USER direct-duplicate
primary USER message-duplicate primary PERSON full-name primary)
CLIPS>
```

### 12.16.18 Getting the List of Facets for a Slot

The slot-facets function returns a multifield value containing the facet values for the specified slot
(the slot can be inherited or explicitly defined for the class). A multifield value of length zero is
returned if an error occurs. The following table lists the meaning of each field position and its
possible values.

```
Field Meaning Values Explanation
1 Field Type SGL/MLT Single-field or multifield
2 Default Value STC/DYN/NIL Static, dynamic, or none
3 Inheritance INH/NIL Inheritable by other classes or not
4 Access RW/R/INT Read-write, read-only, or initialize-only
5 Storage LCL/SHR Local or shared
6 Pattern-Match RCT/NIL Reactive or non-reactive
7 Source EXC/CMP Exclusive or composite
8 Visibility PUB/PRV Public or private
9 Automatic Accessors R/W/RW/NIL Read, write, read-write, or none
10 Override-Message <message-name> Name of message sent for slot-overrides
```

Syntax

```
(slot-facets <class-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass PERSON
```

```
CLIPS Basic Programming Guide 263
```

```
(is-a USER)
(multislot full-name))
CLIPS> (slot-facets PERSON full-name)
(MLT STC INH RW LCL RCT EXC PRV RW put-full-name)
CLIPS>
```

### 12.16.19 Getting the List of Source Classes for a Slot

The slot-sources function returns a multifield value containing the names of the classes which
provide facets for a slot of the specified class. In the case of an exclusive slot, this multifield will
be of length one and contain the name of the contributing class. However, composite slots may
have facets from many different classes. A multifield of length zero is returned if an error occurs.

Syntax

```
(slot-sources <class-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass PERSON (is-a USER)
(slot full-name (default ""))
(slot age (default 0)))
CLIPS>
(defclass LOCKED-PERSON (is-a PERSON)
(slot full-name
(source composite)
(access initialize-only)))
CLIPS> (slot-sources PERSON full-name)
(PERSON)
CLIPS> (slot-sources LOCKED-PERSON full-name)
(PERSON LOCKED-PERSON)
CLIPS> (slot-sources LOCKED-PERSON age)
(PERSON)
CLIPS>
```

### 12.16.20 Getting the Primitive Types for a Slot

The slot-types function returns a multifield value containing the names of the primitive types
allowed for a slot. A multifield of length zero is returned if an error occurs.

Syntax

```
(slot-types <class-name> <slot-name>)
```

```
264 Section 12: Actions and Functions
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass PERSON
(is-a USER)
(slot full-name (type STRING))
(slot age (type INTEGER)))
CLIPS> (slot-types PERSON full-name)
(STRING)
CLIPS> (slot-types PERSON age)
(INTEGER)
CLIPS>
```

### 12.16.21 Getting the Cardinality for a Slot

The slot-cardinality function returns a multifield value containing the minimum and maximum
cardinality allowed for a multifield slot of the specified class. A maximum cardinality of infinity
is indicated by the symbol +oo (the plus character followed by two lowercase ‘o’ characters—not
zeroes). A multifield of length zero is returned for single field slots or if an error occurs.

Syntax

```
(slot-cardinality <class-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass POLYGON (is-a USER)
(slot sides)
(multislot coordinates
(type INTEGER)
(cardinality 6 ?VARIABLE)))
CLIPS> (slot-cardinality POLYGON sides)
()
CLIPS> (slot-cardinality POLYGON coordinates)
(6 +oo)
CLIPS>
```

### 12.16.22 Getting the Allowed Values for a Slot

The slot-allowed-values function returns a multifield value containing the allowed values for a
slot (specified in any of allowed-... facets for the slots). If no allowed-... facets were specified for
the slot, then the symbol FALSE is returned. A multifield of length zero is returned if an error
occurs.

```
CLIPS Basic Programming Guide 265
```

Syntax

```
(slot-allowed-values <class-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass PERSON (is-a USER)
(slot full-name)
(slot gender (allowed-values male female)))
CLIPS> (slot-allowed-values PERSON full-name)
FALSE
CLIPS> (slot-allowed-values PERSON gender)
(male female)
CLIPS>
```

### 12.16.23 Getting the Numeric Range for a Slot...............................................................

The slot-range function returns a multifield value containing the minimum and maximum numeric
ranges allowed a slot. A minimum value of infinity is indicated by the symbol -oo (the minus
character followed by two lowercase ‘o’ characters—not zeroes). A maximum value of infinity is
indicated by the symbol +oo (the plus character followed by two lowercase ‘o’ characters). The
symbol FALSE is returned for slots in which numeric values are not allowed. A multifield of
length zero is returned if an error occurs.

Syntax

```
(slot-range <class-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass PERSON (is-a USER)
(slot full-name (type STRING))
(slot age (type INTEGER) (range 0 120))
(slot net-worth (type FLOAT)))
CLIPS> (slot-range PERSON full-name)
FALSE
CLIPS> (slot-range PERSON age)
(0 120)
CLIPS> (slot-range PERSON net-worth)
(-oo +oo)
CLIPS>
```

```
266 Section 12: Actions and Functions
```

### 12.16.24 Getting the Default Value for a Slot

The slot-default-value function returns the default value associated with a slot. If a slot has a
dynamic default, the expression will be evaluated when this function is called. The symbol FALSE
is returned if an error occurs.

Syntax

```
(slot-default-value <class-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass ORDER (is-a USER)
(slot id (default-dynamic (gensym)))
(slot item (type STRING) (default ?NONE))
(slot quantity (type INTEGER) (default 1))
(slot details (type STRING)))
CLIPS> (slot-default-value ORDER id)
gen1
CLIPS> (slot-default-value ORDER item)
?NONE
CLIPS> (slot-default-value ORDER quantity)
1
CLIPS> (slot-default-value ORDER details)
""
CLIPS>
```

### 12.16.25 Setting the Defaults Mode for Classes

The set-class-defaults-mode function sets the defaults mode used when classes are defined. The
old mode is the return value of this function.

Syntax

```
(set-class-defaults-mode <mode>)
```

The <mode> term is either the symbol convenience or conservation. By default, the class defaults
mode is convenience. If the mode is convenience, then for the purposes of role inheritance, system
defined class behave as concrete classes; for the purpose of pattern-match inheritance, system
defined classes behave as reactive classes unless the inheriting class is abstract; and the default
setting for the create-accessor facet of the class’ slots is read-write. If the class defaults mode is
conservation, then the role and reactivity of system-defined classes is unchanged for the purposes
of role and pattern-match inheritance and the default setting for the create-accessor facet of the
class’ slots is ?NONE.

```
CLIPS Basic Programming Guide 267
```

### 12.16.26 Getting the Defaults Mode for Classes

The get-class-defaults-mode function returns the current defaults mode used when classes are
defined (convenience or conservation).

Syntax

```
(get-class-defaults-mode)
```

### 12.16.27 Getting the Allowed Classes for a Slot

The slot-allowed-classes function returns a multifield value containing the allowed classes for a
slot (specified by the allowed-classes facet for the slot). If the allowed-classes facet was not
specified for the slot, then the symbol FALSE is returned. A multifield of length zero is returned
if an error occurs.

Syntax

```
(slot-allowed-classes <class-name> <slot-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass ORDER (is-a USER)
(slot item)
(slot quantity))
CLIPS>
(defclass CUSTOMER (is-a USER)
(slot id)
(multislot orders (allowed-classes ORDER)))
CLIPS> (slot-allowed-classes CUSTOMER id)
FALSE
CLIPS> (slot-allowed-classes CUSTOMER orders)
(ORDER)
CLIPS>
```

### 12.1 7 Message-handler Functions

#### 12.17.1 Existence of Shadowed Handlers........................................................................

The next-handlerp function returns the symbol TRUE if there is another message-handler
available for execution; otherwise, it returns the symbol FALSE. If this function is called from an
around handler and there are any shadowed handlers, the return value is the symbol TRUE. If this
function is called from a primary handler and there are any shadowed primary handlers, the return
value is the symbol TRUE. In any other circumstance, the return value is the symbol FALSE.

```
268 Section 12: Actions and Functions
```

Syntax

```
(next-handlerp)
```

#### 12.17.2 Calling Shadowed Handlers

If the conditions are such that the next-handlerp function would return the symbol TRUE, then
calling the call-next-handler function will execute the shadowed method; otherwise, a message
execution error will occur. In the event of an error, the return value of this function is the symbol
FALSE; otherwise, it is the return value of the shadowed handler. The shadowed handler is passed
the same arguments as the calling handler.

A handler may continue execution after calling call-next-handler. In addition, a handler may
make multiple calls to call-next-handler, and the same shadowed handler will be executed each
time.

Syntax

```
(call-next-handler)
```

Example

```
CLIPS> (clear)
CLIPS> (defclass PROCESS (is-a USER))
CLIPS>
(defmessage-handler PROCESS print-args ($?any)
(println "PROCESS: " ?any)
(if (next-handlerp) then
(call-next-handler)))
CLIPS>
(defmessage-handler USER print-args ($?any)
(println "USER: " ?any))
CLIPS> (make-instance p of PROCESS)
[p]
CLIPS> (send [p] print-args 1 2 3 4)
PROCESS: (1 2 3 4)
USER: (1 2 3 4)
CLIPS>
```

#### 12.17.3 Calling Shadowed Handlers with Different Arguments

The override-next-handler function is identical to call-next-handler except that it can change
the arguments passed to the shadowed handler.

Syntax

```
(override-next-handler <expression>*)
```

```
CLIPS Basic Programming Guide 269
```

Example

```
CLIPS> (clear)
CLIPS> (defclass PROCESS (is-a USER))
CLIPS>
(defmessage-handler PROCESS print-args ($?any)
(println "PROCESS: " ?any)
(if (next-handlerp) then
(override-next-handler (rest$ ?any))))
CLIPS>
(defmessage-handler USER print-args ($?any)
(println "USER: " ?any))
CLIPS> (make-instance p of PROCESS)
[p]
CLIPS> (send [p] print-args 1 2 3 4)
PROCESS: (1 2 3 4)
USER: (2 3 4)
CLIPS>
```

### 12.18 Definstances Functions

#### 12.18.1 Getting the List of Definstances

The get-definstances-list function returns a multifield value containing the names of all
definstances constructs visible to the module specified by <module-name> or to the current module
if none is specified. If the symbol \* is specified as the module name, then all definstances are
returned.

Syntax

```
(get-definstances-list [<module-name>])
```

#### 12.18.2 Determining the Module in which a Definstances is Defined

The definstances-module function returns the module in which the specified definstances name
is defined.

Syntax

```
(definstances-module <definstances-name>)
```

```
270 Section 12: Actions and Functions
```

### 12.19 Instance Functions

#### 12.19.1 Initializing an Instance

The init-slots function implements the init message-handler attached to the class USER. This
function evaluates and places slot expressions given by the class definition that were not specified
by slot-overrides in the call to make-instance or initialize-instance. This function should never
be called directly unless an init message-handler is being defined such that the one attached to
USER will never be called. A user-defined class which does not inherit indirectly or directly from
the class USER will require an init message-handler which calls this function in order for instances
of the class to be created. If this function is called from an init message within the context of a
make-instance or initialize-instance call and there are no errors in evaluating the class defaults,
this function will return the address of the instance it is initializing. Otherwise, this function will
return the symbol FALSE.

Syntax

```
(init-slots)
```

#### 12.19.2 Deleting an Instance

The unmake-instance function deletes the specified instances by sending them a delete message.
The argument can be one or more instance-names, instance-addresses, or symbols (an
instance-name without enclosing brackets). The instance specified by the arguments must exist
(except in the case of the symbol _). If the symbol _ is specified for the instance, all instances will
be sent the delete message (unless there is an instance named \*). This function returns the symbol
TRUE if all instances were successfully deleted, otherwise it returns the symbol FALSE. Note,
this function is exactly equivalent to sending the instance(s) the delete message directly and is
provided only as an intuitive counterpart to the retract function for facts.

Syntax

```
(unmake-instance <instance-expression>+)
```

#### 12.19.3 Deleting the Active Instance from a Handler

The delete-instance function operates implicitly on the active instance for a message, and thus can
only be called from within the body of a message-handler. This function directly deletes the active
instance and is the one used to implement the delete handler attached to class USER. This function
returns the symbol TRUE if the instance was successfully deleted; otherwise, it returns the symbol
FALSE.

```
CLIPS Basic Programming Guide 271
```

Syntax

```
(delete-instance)
```

#### 12.19.4 Determining the Class of an Object

The class function returns a symbol which is the name of the class of its argument. It returns the
symbol FALSE on errors. This function is equivalent to the type function.

Syntax

```
(class <object-expression>)
```

Example

```
CLIPS> (class 34)
INTEGER
CLIPS>
```

#### 12.19.5 Determining the Name of an Instance

The instance-name function returns a symbol which is the name of its instance argument. It returns
the symbol FALSE on errors. The evaluation of the argument must be an instance-name or
instance-address of an existing instance.

Syntax

```
(instance-name <instance-expression>)
```

#### 12.19.6 Determining the Address of an Instance

The instance-address function returns the address of its instance argument. It returns the symbol
FALSE on errors. The evaluation of <instance expression> must be an instance-name or
instance-address of an existing instance. If <module> or the symbol _ is not specified, the function
searches only in the current module. If the symbol _ is specified, the current module and imported
modules are recursively searched. If <module> is specified, only that module is searched. The ::
syntax cannot be used with the instance-name if <module> or \* is specified.

Syntax

```
(instance-address [<module> | *] <instance-expression>)
```

```
272 Section 12: Actions and Functions
```

#### 12.19.7 Converting a Symbol to an Instance-Name

The symbol-to-instance-name function returns an instance-name which is equivalent to its
symbol argument. It returns the symbol FALSE on errors.

Syntax

```
(symbol-to-instance-name <symbol-expression>)
```

Example

```
CLIPS> (symbol-to-instance-name (sym-cat abc def))
[abcdef]
CLIPS>
```

#### 12.19.8 Converting an Instance-Name to a Symbol

The instance-name-to-symbol function returns a symbol which is equivalent to its instance-name
argument. It returns the symbol FALSE on errors.

Syntax

```
(instance-name-to-symbol <instance-name-expression>)
```

Example

```
CLIPS> (instance-name-to-symbol [a])
a
CLIPS>
```

#### 12.19.9 Testing for an Instance

The instancep function returns the symbol TRUE if the evaluation of its argument is an
instance-address or an instance-name; otherwise, it returns the symbol FALSE.

Syntax

```
(instancep <expression>)
```

#### 12.19.10 Testing for an Instance-Address

The instance-addressp function returns the symbol TRUE if the evaluation of its argument is an
instance-address; otherwise, it returns the symbol FALSE.

```
CLIPS Basic Programming Guide 273
```

Syntax

```
(instance-addressp <expression>)
```

#### 12.19.11 Testing for an Instance-Name

The instance-namep function returns the symbol TRUE if the evaluation of its argument is an
instance-name; otherwise, it returns the symbol FALSE.

Syntax

```
(instance-namep <expression>)
```

#### 12.19.12 Testing for the Existence an Instance

The instance-existp function returns the symbol TRUE if the specified instance exists; otherwise,
it returns the symbol FALSE. If the argument is an instance-name, the function determines if an
instance of the specified name exists. If the argument is an instance-address, the function
determines if the specified address is still valid.

Syntax

```
(instance-existp <instance-expression>)
```

#### 12.19.13 Reading a Slot Value

The dynamic-get function returns the value of the specified slot of the active instance. If the slot
does not exist, the slot does not have a value, or this function is called from outside a
message-handler, this function will return the symbol FALSE and an error will be generated. This
function differs from the ?self:<slot-name> syntax in that the slot is not looked up until the function
is actually called. Thus it is possible to access different slots every time the function is executed.
This function bypasses message-passing.

Syntax

```
(dynamic-get <slot-name-expression>)
```

#### 12.19.14 Setting a Slot Value

The dynamic-put function sets the value of the specified slot of the active instance. If the slot does
not exist, there is an error in evaluating the arguments to be placed, or this function is called from
outside a message-handler, this function will return the symbol FALSE and an error will be
generated. Otherwise, the new slot value is returned. This function differs from the (bind

```
274 Section 12: Actions and Functions
```

?self:<slot-name> <value>\*) syntax in that the slot is not looked up until the function is actually
called. Thus it is possible to access different slots every time the function is executed. This function
bypasses message-passing.

Syntax

```
(dynamic-put <slot-name-expression> <expression>*)
```

#### 12.19.15 Replacing Fields in a Slot

The slot-replace$ and slot-direct-replace$ functions allow the replacement of a range of fields in
a multifield slot value with one or more new values. The range indices must be from 1 to n, where
n is the number of fields in the multifield slot’s original value and n > 0.

The slot-replace$ function sets the new slot value with a put- message. The slot-direct-replace$
function can only be called from message-handlers and sets the new slot value for the active
instance directly. Both functions read the original value of the slot directly without the use of a
get- message and return the new slot value on success and the symbol FALSE on errors.

Syntax

```
(slot-replace$ <instance-expression> <mv-slot-name>
<range-begin> <range-end> <expression>+)
```

```
(slot-direct-replace$ <mv-slot-name>
<range-begin> <range-end> <expression>+)
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass LIST (is-a USER)
(multislot items))
CLIPS> (make-instance gl of LIST (items milk eggs cheese))
[gl]
CLIPS> (slot-replace$ gl items 2 2 beer pretzels)
(milk beer pretzels cheese)
CLIPS>
```

#### 12.19.16 Inserting Fields in a Slot

The slot-insert$ and slot-direct-insert$ functions allow the insertion of one or more new values
in a multifield slot value before a specified field index. The index must greater than or equal to 1.
A value of 1 inserts the new value(s) at the beginning of the slot’s value. Any value greater than
the length of the slot’s value appends the new values to the end of the slot’s value.

```
CLIPS Basic Programming Guide 275
```

The slot-insert$ function sets the new slot value with a put- message. The slot-direct-insert$
function can only be called from message-handlers and sets the new slot value for the active
instance directly. Both functions read the original value of the slot directly without the use of a
get- message and return the new slot value on success and the symbol FALSE on errors.

Syntax

```
(slot-insert$ <instance-expression> <mv-slot-name>
<index> <expression>+)
```

```
(slot-direct-insert$ <mv-slot-name> <index> <expression>+)
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass LIST (is-a USER)
(multislot items))
CLIPS> (make-instance gl of LIST (items milk eggs cheese))
[gl]
CLIPS> (slot-insert$ [gl] items 2 beer pretzels)
(milk beer pretzels eggs cheese)
CLIPS>
```

#### 12.19.17 Deleting Fields in a Slot

The slot-delete$ and slot-direct-delete$ functions allow the deletion of a range of fields in a
multifield slot value. The range indices must be from 1..n, where n is the number of fields in the
multifield slot’s original value and n > 0.

The slot-delete$ function sets the new slot value with a put- message. The slot-direct-delete$
function can only be called from message-handlers and sets the new slot value for the active
instance directly. Both functions read the original value of the slot directly without the use of a
get- message and return the new slot value on success and the symbol FALSE on errors.

Syntax

```
(slot-delete$ <instance-expression> <mv-slot-name>
<range-begin> <range-end>)
```

```
(slot-direct-delete$ <mv-slot-name> <range-begin> <range-end>)
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass LIST (is-a USER)
(multislot items))
```

```
276 Section 12: Actions and Functions
```

```
CLIPS> (make-instance gl of LIST (items milk eggs cheese))
[gl]
CLIPS> (slot-delete$ [gl] items 2 3)
(milk)
CLIPS>
```

### 12.20 Defmodule Functions

The following functions provide ancillary capabilities for the defmodule construct.

#### 12.20.1 Getting the List of Defmodules...........................................................................

The get-defmodule-list function returns a multifield value containing the names of all defmodules
that are currently defined.

Syntax

```
(get-defmodule-list)
```

Example

```
CLIPS> (clear)
CLIPS> (get-defmodule-list)
(MAIN)
CLIPS> (defmodule COLLECT)
CLIPS> (defmodule PROCESS)
CLIPS> (get-defmodule-list)
(MAIN COLLECT PROCESS)
CLIPS>
```

#### 12.20.2 Setting the Current Module

The set-current-module function sets the current module. It returns the name of the previous
current module. If an invalid module name is given, then the current module is not changed and
the name of the current module is returned.

Syntax

```
(set-current-module <defmodule-name>)
```

#### 12.20.3 Getting the Current Module

The get-current-module function returns the name of the current module.

```
CLIPS Basic Programming Guide 277
```

Syntax

```
(get-current-module)
```

### 12.21 Sequence Expansion

By default, there is no distinction between single-field and multifield variable references within
function calls (as opposed to declaring variables for function parameters or variables used for
pattern-matching). For example:

```
CLIPS> (clear)
CLIPS>
(defrule print-list
(grocery-list $?groceries)
=>
(println ?groceries)
(println $?groceries))
CLIPS> (assert (grocery-list milk eggs cheese))
<Fact-1>
CLIPS> (run)
(milk eggs cheese)
(milk eggs cheese)
CLIPS>
```

Note that both printout statements in the rule produce identical output when the rule executes. The
use of ?groceries and $?groceries within the function call behave identically.

Multifield variable references within function calls, however, can optionally be expanded into
multiple single field arguments. The $ acts as a “sequence expansion” operator and has special
meaning when applied to a global or local variable reference within the argument list of a function
call. The $ means to take the fields of the multifield value referenced by the variable and treat them
as separate arguments to the function as opposed to passing a single multifield value argument.

For example, using sequence expansion with the print-list rule would give the following output:

```
CLIPS> (clear)
CLIPS> (set-sequence-operator-recognition TRUE)
FALSE
CLIPS>
(defrule print-list
(grocery-list $?groceries)
=>
(println ?groceries)
(println $?groceries))
CLIPS> (assert (grocery-list milk eggs cheese))
<Fact-1>
CLIPS> (run)
(milk eggs cheese)
```

```
278 Section 12: Actions and Functions
```

```
milkeggscheese
CLIPS> (set-sequence-operator-recognition FALSE)
TRUE
CLIPS>
```

Using sequence expansion, the two printout statements on the RHS of the expansion rule are
equivalent to:

```
(println (create$ milk eggs cheese))
(println milk eggs cheese)
```

The $ operator also works with global variables. For example:

```
CLIPS> (clear)
CLIPS> (set-sequence-operator-recognition TRUE)
FALSE
CLIPS> (defglobal ?*sides* = (create$ 3 4 5))
CLIPS> (+ ?*sides*)
[ARGACCES1] Function '+' expected at least 2 arguments.
CLIPS> (+ $?*sides*)
12
CLIPS> (set-sequence-operator-recognition FALSE)
TRUE
CLIPS>
```

The sequence expansion operator is particularly useful for generic function methods. Consider the
ease now of defining a general addition function for strings.

```
CLIPS> (clear)
CLIPS> (set-sequence-operator-recognition TRUE)
TRUE
CLIPS>
(defmethod + (($?any STRING))
(str-cat $?any))
CLIPS> (+ "red" "white" "blue")
"redwhiteblue"
CLIPS> (set-sequence-operator-recognition FALSE)
TRUE
CLIPS>
```

By default, sequence expansion is disabled. The behavior can be enabled using the
set-sequence-operator-recognition function.

#### 12.21.1 Sequence Expansion and Rules

Sequence expansion is allowed on the LHS of rules, but only within function calls. If a variable is
specified in a pattern as a single or multifield variable, then all other references to that variable
that are not within function calls must also be the same. For example, the following rule is not
allowed

```
CLIPS Basic Programming Guide 279
```

```
(defrule bad-rule
(pattern $?x ?x $?x)
=>)
```

The following rule illustrates appropriate use of sequence expansion on the LHS of rules.

```
(defrule good-rule- 1
(pattern $?x&:(> (length$ ?x) 1))
(another-pattern $?y&:(> (length$ ?y) 1))
(test (> (+ $?x) (+ $?y)))
=>)
```

The first and second patterns use the length$ function to determine that the multifields bound to
?x and ?y are greater than 1. Sequence expansion is not used to pass ?x and ?y to the length$
function since the length$ function expects a single argument of type multifield. The test CE calls
the + function to determine the sum of the values bound to ?x and ?y. Sequence expansion is used
for these function calls since the + function expects two or more arguments with numeric data
values.

Sequence expansion has no affect within an assert, modify, or duplicate; however, it can be used
with other functions on the RHS of a rule.

#### 12.21.2 Multifield Expansion Function

The $ operator is merely a shorthand notation for the expand$ function call. For example, the
function calls

```
(println $?b)
```

and

```
(println (expand$ ?b))
```

are identical.

Syntax

```
(expand$ <multifield-expression>)
```

The expand$ function is valid only within the argument list of a function call. The expand$
function (and hence sequence expansion) cannot be used as an argument to the following
functions: expand$, return, progn, while, if, progn$, foreach, switch, loop-for-count, assert,
modify, duplicate and object-pattern-match-delay.

```
280 Section 12: Actions and Functions
```

#### 12.21.3 Setting The Sequence Operator Recognition Behavior

The set-sequence-operator-recognition function sets the sequence operator recognition behavior.
When this behavior is disabled (FALSE by default), multifield variables found in function calls
are treated as a single argument. When this behaviour is enabled, multifield variables are expanded
and passed as separate arguments in the function call. This behavior should be set before an
expression references a multifield variable is encountered (i.e. changing the behavior does not
retroactively change the behavior for previously encountered expressions). The return value for
this function is the old value for the behavior.

Syntax

```
(set-sequence-operator-recognition <boolean-expression>)
```

#### 12.21.4 Getting The Sequence Operator Recognition Behavior......................................

The get-sequence-operator-recognition function returns the current value of the sequence
operator recognition behavior (either the symbol TRUE or FALSE).

Syntax

```
(get-sequence-operator-recognition)
```

#### 12.21.5 Sequence Operator Caveat

CLIPS normally tries to detect as many constraint errors as possible for a function call at parse
time, such as the wrong number of arguments or argument types. However, if the sequence
expansion operator is used in the function call, all such checking is delayed until run-time (because
the number and types of arguments can change for each execution of the call.) For example:

```
CLIPS> (clear)
CLIPS> (set-sequence-operator-recognition TRUE)
FALSE
CLIPS> (deffunction f1 (?a ?b))
CLIPS> (deffunction f2 ($?a) (f1 ?a))
[ARGACCES1] Function 'f1' expected exactly 2 arguments.
```

```
ERROR:
(deffunction MAIN::f2
($?a)
(f1 ?a)
CLIPS> (deffunction f2 ($?a) (f1 $?a))
CLIPS> (f2 1)
[ARGACCES1] Function 'f1' expected exactly 2 arguments.
[PRCCODE4] Execution halted during the actions of deffunction 'f2'.
FALSE
CLIPS> (f2 1 2)
```

CLIPS Basic Programming Guide 281

```
FALSE
CLIPS> (set-sequence-operator-recognition FALSE)
TRUE
CLIPS>
```

```
282 Section 13: Commands
```

## Section 13: Commands

This section describes commands primarily intended for use from the REPL. These commands
may also be used from constructs and other places where functions can be used.

### 13.1 Environment Commands

The following commands control the CLIPS environment.

#### 13.1.1 Loading Constructs From A File

The load command compiles the construct definitions stored in the file specified by the
<file-name> argument. If the compilations item is being watched as a result of the watch
command, then an informational message (including the type and name of the construct) will be
displayed for each construct loaded. If the compilations item is not being watched, then a character
is printed for each construct loaded (“\*” for defrule, “$” for deffacts, “%” for deftemplate, “:” for
defglobal, “!” for deffunction, “^” for defgeneric, “&” for defmethod, “#” for defclass, “~” for
defmessage-handler, “@” for definstances, and “+” for defmodule). This command returns the
symbol TRUE if the file was successfully loaded, otherwise FALSE is returned.

Syntax

```
(load <file-name>)
```

#### 13.1.2 Loading Constructs From A File without Progress Information

The load\* command compiles the construct definitions stored in the file specified by the
<file-name> argument; however, unlike the load command, informational messsages are not
printed to show the progress of compiling the file. Error messages are still printed if errors are
encountered while loading the file. This command returns the symbol TRUE if the file was
successfully loaded; otherwise, it returns the symbol FALSE.

Syntax

```
(load* <file-name>)
```

```
CLIPS Basic Programming Guide 283
```

#### 13.1.3 Saving All Constructs To A File

The save command writes all construct definitions to the file specified by the <file-name>
argument, overwriting the file if it already exists. This command returns the symbol TRUE if the
file was successfully saved; otherwise it returns the symbol FALSE. If the conserve-mem
command has been set to the symbol on, then the text representation of construct definitions is not
saved when they are compiled and the save command will have no output.

Syntax

```
(save <file-name>)
```

#### 13.1.4 Loading a Binary Image........................................................................................

The bload command loads the precompiled constructs stored in the binary file specified by the
<file-name> argument. The specified file must have been created by the bsave command. Loading
a binary file is quicker than using the load command to load a UTF- 8 text file. A bload clears all
constructs (as well as all facts and instances). The only constructive/destructive operation that can
occur after a bload is the clear command or the bload command (which clears the current binary
image). This means that constructs cannot be loaded or deleted while a bload is in effect. In order
to add constructs to a binary image, the original ASCII text file must be reloaded, the new
constructs added, and then another bsave must be performed. This command returns the symbol
TRUE if the file was successfully bloaded, otherwise FALSE is returned.

Binary images can be loaded into different compile-time configurations of CLIPS, as long as the
same version of CLIPS is used and all the functions and constructs needed by the binary image are
supported. In addition, binary images should theoretically work across different hardware
platforms if internal data representations are equivalent (e.g. same integer size, same byte order,
same floating-point format, etc), however, this is not recommended.

Syntax

```
(bload <file-name>)
```

#### 13.1.5 Saving a Binary Image

The bsave command writes all of the construct definitions currently loaded to the file specified by
the <file-name> argument. The saved file is written using a binary format which results in faster
load time. The text representation of construct definitions is not saved with a binary image (thus,
commands like ppdefrule will show no output for any of the rules in the binary image). In addition,
constraint information associated with constructs is not saved to the binary image unless dynamic
constraint checking is enabled (using the set-dynamic-constraint-checking command). This

```
284 Section 13: Commands
```

command returns the symbol TRUE if the file was successfully saved; otherwise, it returns the
symbol FALSE.

Syntax

```
(bsave <file-name>)
```

13.1.6 Clearing CLIPS

The clear command removes all constructs and associated data (such as facts and instances). A
clear may be performed safely at any time, however, certain constructs will not allow themselves
to be deleted while they are in use. For example, while deffacts are being reset (by the reset
command), it is not possible to remove them using the clear command. Note that the clear
command does not effect many environment characteristics (such as the current conflict resolution
strategy). This command has no return value.

Syntax

```
(clear)
```

### 13.1.7 Exiting CLIPS

The exit command terminates CLIPS execution. This command has no return value.

Syntax

```
(exit [<integer-expression>])
```

The optional <integer-expression> argument allows the exit status code to be specified and is
passed to the C exit function.

### 13.1.8 Resetting CLIPS....................................................................................................

The reset command removes all activations from the agenda, retracts all facts, deletes all instances,
assigns global variables their initial values, asserts all facts from deffacts constructs, creates all
instances from definstances constructs, and sets the current module and focus to the MAIN
module. Note that the reset command does not effect many environment characteristics (such as
the current conflict resolution strategy). This command has no return value.

Syntax

```
(reset)
```

```
CLIPS Basic Programming Guide 285
```

### 13.1.9 Executing Commands From a File

The batch command allows automatic processing of CLIPS interactive commands by replacing
standard input with the contents of a file. Any command or function can be used in a batch file, as
well as construct definitions and responses to functions that read input from standard input such
as the read and readline functions. The load command should be used in batch files rather than
defining constructs directly—the load command expects only constructs and provides better error
recovery when parentheses are misplaced; the batch command, however, moves on until it finds
the next construct or command (and in the case of a construct this is likely to generate more errors
as the remaining commands and functions in the construct are parsed). This command returns the
symbol TRUE if the batch file was successfully executed; otherwise, it returns the symbol
FALSE.

Note that the batch command operates by replacing standard input rather than by immediately
executing the commands found in the batch file. Thus, if you execute a batch command from the
RHS of a rule, the commands in that batch file will not be processed until control is returned to the
top-level prompt.

Syntax

```
(batch <file-name>)
```

### 13.1.10 Executing Commands From a File Without Replacing Standard Input

The batch* command evaluates the series of commands stored in the file specified by the
<file-name> argument. Unlike the batch command, the batch* command evaluates all of the
commands in the specified file before returning. The batch* command does not replace standard
input and thus a batch* file cannot be used to provide input to functions such as read and readline.
In addition, commands stored in the batch\* file and the return value of these commands are not
echoed to standard output.

Syntax

```
(batch* <file-name>)
```

### 13.1.11 Determining CLIPS Compilation Options

The options command prints the compiler flag settings (for enabling/disabling various features)
used for creating the CLIPS executable.

Syntax

```
(options)
```

```
286 Section 13: Commands
```

### 13.1.12 Calling the Operating System

The system command allows a call to the operating system. If no arguments are specified, the
function returns 0 if a command processer is unavailable; otherwise, it returns a non-zero value. If
one or more string/symbol arguments are specified, the arguments are concatenated into a single
command string and this string is then passed to the command processor. In this case, the function
returns an integer value indicating the completion status of the command (which can vary
depending upon your operating system and compiler). If any invalid arguments are specified, this
command returns the symbol FALSE.

Syntax

```
(system <lexeme-expression>*)
```

Example

```
(defrule print-directory
(print-directory ?directory)
=>
(system "dir " ?directory))
```

Note that any spaces needed for a proper parsing of the system command must be added by the
user in the call to the system command. Also note that the system command is not guaranteed to
execute (e.g., the operating system may not have enough memory to spawn a new process).

❖ Portability Note

The system function uses the ANSI C function system as a base. The return value of this ANSI
library function is implementation dependent and may change for different operating systems and
compilers.

### 13.1.13 Setting the Dynamic Constraint Checking Behavior

The set-dynamic-constraint-checking function sets the dynamic constraint checking behavior.
When this behavior is disabled (FALSE by default), newly created facts and instances do not have
their slot values checked for constraint violations. When this behavior is enabled (TRUE), the slot
values are checked for constraint violations. The return value for this command is the old value
for the behavior. Constraint information is not saved when using the bload and constructs-to-c
command if dynamic constraint checking is disabled.

Syntax

```
(set-dynamic-constraint-checking <boolean-expression>)
```

```
CLIPS Basic Programming Guide 287
```

### 13.1.14 Getting the Dynamic Constraint Checking Behavior

Thze get-dynamic-constraint-checking function returns the current value of the dynamic
constraint checking behavior (the symbol TRUE or FALSE).

Syntax

```
(get-dynamic-constraint-checking)
```

### 13.1.15 Finding Symbols

The apropos command displays all symbols currently defined in CLIPS which contain a
specified substring. This command has no return value.

Syntax

```
(apropos <lexeme>)
```

Example

```
CLIPS> (apropos pen)
dependencies
dependents
open
CLIPS>
```

## 13.2 Debugging Commands...................................................................................................

The following commands control the CLIPS debugging features.

### 13.2.1 Generating Trace Files

The dribble-on command sends all output normally sent to the logical names stdout, werror, and
wwarning to the file specified by the <file-name> argument as well as sending output to its normal
destination. Additionally, all information received from logical name stdin is also sent to the file
specified by the <file-name> argument as well as being returned to the requesting function. This
command returns the symbol TRUE if the dribble file was successfully opened; otherwise, it
returns the symbol FALSE.

Syntax

```
(dribble-on <file-name>)
```

```
288 Section 13: Commands
```

### 13.2.2 Closing Trace Files

The dribble-off command stops sending output to the dribble file and closes it. This command
returns the symbol TRUE if the dribble file was successfully closed; otherwise, it returns the
symbol FALSE.

Syntax

```
(dribble-off)
```

### 13.2.3 Enabling Watch Items

The watch command function enables debugging/informational output for various CLIPS
operations.

Syntax

```
(watch <watch-item>)
```

```
<watch-item> ::= all |
compilations |
statistics |
focus |
messages |
deffunctions <deffunction-name>* |
globals <global-name>* |
rules <rule-name>* |
activations <rule-name>* |
facts <deftemplate-name>* |
instances <class-name>* |
slots <class-name>* |
message-handlers <handler-spec-1>*
[<handler-spec-2>]) |
generic-functions <generic-name>* |
methods <method-spec-1>* [<method-spec-2>]
```

```
<handler-spec-1> ::= <class-name>
<handler-name> <handler-type>
<handler-spec-2> ::= <class-name>
[<handler-name> [<handler-type>]]
```

```
<method-spec-1> ::= <generic-name> <method-index>
<method-spec-2> ::= <generic-name> [<method-index>]
```

If compilations are watched, the progress of construct definitions will be displayed.

If facts are watched, all fact assertions and retractions will be displayed. Optionally, facts
associated with individual deftemplates can be watched by specifying one or more deftemplate
names.

```
CLIPS Basic Programming Guide 289
```

If rules are watched, all rule firings will be displayed. If activations are watched, all rule
activations and deactivations will be displayed. Optionally, rule firings and activations associated
with individual defrules can be watched by specifying one or more defrule names. If statistics are
watched, timing information along with other information (average number of facts, average
number of activations, etc.) will be displayed after a run. Note that the number of rules fired and
timing information is not printed unless this item is being watch. If focus is watched, then changes
to the current focus will be displayed.

If globals are watched, variable assignments to globals variables will be displayed. Optionally,
variable assignments associated with individual defglobals can be watched by specifying one or
more defglobal names. If deffunctions are watched, the start and finish of deffunctions will be
displayed. Optionally, the start and end display associated with individual deffunctions can be
watched by specifying one or more deffunction names.

If generic-functions are watched, the start and finish of generic functions will be displayed.
Optionally, the start and end display associated with individual defgenerics can be watched by
specifying one or more defgeneric names. If methods are watched, the start and finish of individual
methods within a generic function will be displayed. Optionally, individual methods can be
watched by specifying one or more methods using a defgeneric name and a method index. When
the method index is not specified, then all methods of the specified defgeneric will be watched.

If instances are watched, creation and deletion of instances will be displayed. If slots are watched,
changes to any instance slot values will be displayed. Optionally, instances and slots associated
with individual concrete defclasses can be watched by specifying one or more concrete defclass
names. If message-handlers are watched, the start and finish of individual message-handlers
within a message will be displayed. Optionally, individual message-handlers can be watched by
specifying one or more message-handlers using a defclass name, a message-handler name, and a
message-handler type. When the message-handler name and message-handler type are not
specified, then all message-handlers for the specified class will be watched. When the
message-handler type is not specified, then all message-handlers for the specified class with the
specified message-handler name will be watched. If messages are watched, the start and finish of
messages will be displayed.

For the watch items that allow individual constructs to be watched, if no constructs are specified,
then all constructs of that type will be watched. If all constructs associated with a watch item are
being watched, then newly defined constructs of the same type will also be watched. A construct
retains its old watch state if it is redefined. If all is watched, then all other watch items will be
watched. By default, no items are watched. The watch command has no return value.

Example

```
CLIPS> (watch rules)
```

```
290 Section 13: Commands
```

```
CLIPS>
```

### 13.2.4 Disabling Watch Items

The unwatch command disables the effect of the watch command for the specified watch item.

Syntax

```
(unwatch <watch-item>)
```

This command is identical to the watch command with the exception that it disables watch items
rather than enabling them. This command has no return value.

Example

```
CLIPS> (unwatch all)
CLIPS>
```

### 13.2.5 Viewing the Current State of Watch Items

The list-watch-items command displays the current state of watch items.

Syntax

```
(list-watch-items [<watch-item>])
```

The list-watch-items command displays the current state of all watch items. If called without the
<watch-item> argument, the global watch state of all watch items is displayed. If called with the
<watch-item> argument, the global watch state for that item is displayed followed by the individual
watch states for each item of the specified type which can be watched. This command has no return
value.

Example

```
CLIPS> (list-watch-items)
facts = off
instances = off
slots = off
rules = off
activations = off
messages = off
message-handlers = off
generic-functions = off
methods = off
deffunctions = off
compilations = off
statistics = off
globals = off
```

```
CLIPS Basic Programming Guide 291
```

```
focus = off
CLIPS> (list-watch-items facts)
facts = off
MAIN:
CLIPS>
```

## 13.3 Deftemplate Commands.................................................................................................

The following commands manipulate deftemplates.

### 13.3.1 Displaying the Text of a Deftemplate

The ppdeftemplate command sends the source text of a deftemplate to a logical name as output.
If the <logical-name> argument is t or unspecified, then output is sent to the logical name stdout,
otherwise it is sent to the specified logical name. If the logical name nil is used, then the text is
used as the return value of this command rather than being sent to an output destination; otherwise
this command has no return value.

Syntax

```
(ppdeftemplate <deftemplate-name> [<logical-name>])
```

### 13.3.2 Displaying the List of Deftemplates

The list-deftemplates command displays the names of all deftemplates. This command has no
return value.

Syntax

```
(list-deftemplates [<module-name>])
```

If the <module-name> argument is unspecified, then the names of all deftemplates in the current
module are displayed. If the <module-name> argument is specified, then the names of all
deftemplates in the specified module are displayed. If the <module-name> argument is the symbol
\*, then the names of all deftemplates in all modules are displayed.

### 13.3.3 Deleting a Deftemplate

The undeftemplate command deletes a previously defined deftemplate.

Syntax

```
(undeftemplate <deftemplate-name>)
```

```
292 Section 13: Commands
```

If the deftemplate is in use (for example by a fact or a rule), then the deletion will fail. Otherwise,
no further uses of the deleted deftemplate are permitted (unless redefined). If the symbol _ is used
for the <deftemplate-name> argument, then all deftemplates will be deleted (unless there is a
deftemplate named _). This command has no return value.

## 13.4 Fact Commands

The following commands display information about facts.

### 13.4.1 Displaying the Fact-List

The facts command lists existing facts.

Syntax

```
(facts [<module-name>]
[<start-integer-expression>
[<end-integer-expression>
[<max-integer-expression>]]])
```

If the <module-name> argument is not specified, then only facts visible to the current module will
be displayed. If the <module-name> argument is specified, then only facts visible to the specified
module are displayed. If the symbol \* is used for the <module-name> argument, then facts from
any module may be displayed. If the start argument is specified, only facts with fact-indices greater
than or equal to this argument are displayed. If the end argument is specified, only facts with
fact-indices less than or equal to this argument are displayed. If the max argument is specified,
then no facts will be displayed beyond the specified maximum number of facts to be displayed.
This command has no return value.

### 13.4.2 Displaying a Single Fact

The ppfact command displays a single fact, placing each slot and its value on a separate line.
Optionally the logical name to which output is sent can be specified and slots containing their
default values can be excluded from the output. If the <logical-name> argument is t or unspecified,
then output is sent to the logical name stdout, otherwise it is sent to the specified logical name. If
the logical name nil is used, then the construct’s text is used as the return value of this command
rather than being sent to an output destination; otherwise this command has no return value.

If the <ignore-defaults-flag> argument is the symbol FALSE or unspecified, then all of the fact’s
slots are displayed, otherwise slots with static defaults are only displayed if their current slot value
differs from their initial default value.

```
CLIPS Basic Programming Guide 293
```

Syntax

```
(ppfact <fact-specifier> [<logical-name> [<ignore-defaults-flag>]])
```

Example

```
CLIPS> (clear)
CLIPS>
(deftemplate person
(multislot name)
(slot age (default 0))
(slot net-worth (default 0.0)))
CLIPS> (assert (person))
<Fact-1>
CLIPS> (ppfact 1 t)
(person
(name)
(age 0)
(net-worth 0.0))
CLIPS> (ppfact 1 t TRUE)
(person)
CLIPS> (modify 1 (name John Smith) (age 23))
<Fact-1>
CLIPS> (ppfact 1 t TRUE)
(person
(name John Smith)
(age 23))
CLIPS> (ppfact 1 nil)
"(person
(name John Smith)
(age 23)
(net-worth 0.0))"
CLIPS>
```

### 13.4.3 Saving Facts To A Text File

The save-facts command saves all of the facts in the current fact-list into the file specified by the
<file-name> argument. External-address and fact-address fields are saved as strings.
Instance-address fields are converted to instance-names. Optionally, the scope of facts to be saved
can be specified. If the <save-scope> argument is the symbol visible, then all facts visible to the
current module are saved. If the <save-scope> argument is the symbol local, then only those facts
with deftemplates defined in the current module are saved. If the <save-scope> argument is not
specified, it defaults to local. If the <save-scope> argument is specified, then one or more
deftemplate names may also be specified. In this event, only those facts associated with a
corresponding deftemplate in the specified list will be saved. This command returns the number
of facts saved.

```
294 Section 13: Commands
```

Syntax

```
(save-facts <file-name> [<save-scope> <deftemplate-names>*])
```

```
<save-scope> ::= visible | local
```

### 13.4.4 Saving Facts to a Binary File

The bsave-facts commands works exactly like save-facts command except that the facts are saved
in a binary format which can only be loaded with the bload-facts command. The advantage to this
format is that loading binary facts can be much faster than loading text facts for large numbers of
facts. The disadvantage is that the file is not portable to other platforms.

Syntax

```
(bsave-facts <file-name> [<save-scope> <deftemplate-names>*])
```

### 13.4.5 Loading Facts From a Text File

The load-facts command will read facts in text format from the file specified by the <file-name>
argument and assert them. It can read files created with the save-facts command or any UTF- 8
text file with facts in the correct format. Facts may span across lines and can be written in either
ordered or deftemplate format. This command returns the number of facts loaded or -1 if it could
not access the fact file.

Syntax

```
(load-facts <file-name>)
```

Example

```
CLIPS> (clear)
CLIPS> (deftemplate person (slot name) (slot age))
CLIPS> (open "facts.fct" facts "w")
TRUE
CLIPS> (printout facts "(person (name Jack) (age 23))" crlf)
CLIPS> (printout facts "(person (name Jill) (age 34))" crlf)
CLIPS> (close facts)
TRUE
CLIPS> (load-facts facts.fct)
2
CLIPS> (facts)
f- 1 (person (name Jack) (age 23))
f-2 (person (name Jill) (age 34))
For a total of 2 facts.
CLIPS>
```

```
CLIPS Basic Programming Guide 295
```

### 13.4.6 Loading Facts from a Binary File

The bload-facts command works exactly like load-facts except that it can only work with files
generated by bsave-facts. This command returns the number of facts loaded or -1 if it could not
access the fact file.

Syntax

```
(bload-facts <file-name>)
```

### 13.4.7 Setting the Duplication Behavior of Facts

The set-fact-duplication command sets fact duplication behavior. When this behavior is disabled
(FALSE by default), asserting a duplicate of a fact already in the fact-list produces no effect.
When enabled (TRUE), the duplicate fact is asserted with a new fact-index. The return value for
this command is the old value for the behavior.

Syntax

```
(set-fact-duplication <boolean-expression>)
```

Example

```
CLIPS> (clear)
CLIPS> (get-fact-duplication)
FALSE
CLIPS> (watch facts)
CLIPS> (assert (grocery-list milk eggs cheese))
==> f-1 (grocery-list milk eggs cheese)
<Fact-1>
CLIPS> (assert (grocery-list milk eggs cheese))
<Fact-1>
CLIPS> (set-fact-duplication TRUE)
FALSE
CLIPS> (assert (grocery-list milk eggs cheese))
==> f-2 (grocery-list milk eggs cheese)
<Fact-2>
CLIPS> (facts)
f-1 (grocery-list milk eggs cheese)
f-2 (grocery-list milk eggs cheese)
For a total of 2 facts.
CLIPS> (unwatch facts)
CLIPS> (set-fact-duplication FALSE)
TRUE
CLIPS>
```

```
296 Section 13: Commands
```

### 13.4.8 Getting the Duplication Behavior of Facts

The get-fact-duplication command returns the current value of the fact duplication behavior (the
symbol TRUE or FALSE).

Syntax

```
(get-fact-duplication)
```

## 13.5 Deffacts Commands

The following commands manipulate deffacts.

### 13.5.1 Displaying the Text of a Deffacts

The ppdeffacts command sends the source text of a deffacts to a logical name as output. If the
<logical-name> argument is t or unspecified, then output is sent to the logical name stdout,
otherwise it is sent to the specified logical name. If the logical name nil is used, then the text is
used as the return value of this command rather than being sent to an output destination; otherwise
this command has no return value.

Syntax

```
(ppdeffacts <deffacts-name> [<logical-name>])
```

### 13.5.2 Displaying the List of Deffacts

The list-deffacts command displays the names of all defined deffacts.

Syntax

```
(list-deffacts [<module-name>])
```

If the <module-name> argument is unspecified, then the names of all deffacts in the current module
are displayed. If the <module-name> argument is specified, then the names of all deffacts in the
specified module are displayed. If the <module-name> argument is the symbol \*, then the names
of all deffacts in all modules are displayed. This command has no return value.

### 13.5.3 Deleting a Deffacts

The undeffacts command deletes a previously defined deffacts.

```
CLIPS Basic Programming Guide 297
```

Syntax

```
(undeffacts <deffacts-name>)
```

All facts listed in the deleted deffacts construct will no longer be asserted as part of a reset. If the
symbol _ is used for the <deffacts-name> argument, then all deffacts will be deleted (unless there
exists a deffacts named _). This command has no return value.

## 13.6 Defrule Commands

The following commands manipulate defrules.

### 13.6.1 Displaying the Text of a Rule

The ppdefrule command sends the source text of a defrule to a logical name as output. If the
<logical-name> argument is t or unspecified, then output is sent to the logical name stdout,
otherwise it is sent to the specified logical name. If the logical name nil is used, then the text is
used as the return value of this command rather than being sent to an output destination; otherwise
this command has no return value.

Syntax

```
(ppdefrule <rule-name> [<logical-name>])
```

### 13.6.2 Displaying the List of Rules

The list-defrules command displays the names of all defined defrules.

Syntax

```
(list-defrules [<module-name>])
```

If the <module-name> argument is unspecified, then the names of all defrules in the current
module are displayed. If the <module-name> argument is specified, then the names of all defrules
in the specified module are displayed. If the <module-name> argument is the symbol \*, then the
names of all defrules in all modules are displayed. This command has no return value.

### 13.6.3 Deleting a Defrule

The undefrule command deletes a previously defined defrule.

```
298 Section 13: Commands
```

Syntax

```
(undefrule <defrule-name>)
```

If the symbol _ is used for the <defrule-name> argument, then all defrules will be deleted (unless
there is a defrule named _). This command has no return value.

### 13.6.4 Displaying Matches for a Rule

For the specified defrule, the matches command displays the list of the facts or instances which
match each pattern in the rule’s LHS, the partial matches for the rule, and the activations for the
rule. When listed as a partial match, the not, exists, and forall CEs are shown as an asterisk. This
command returns the symbol FALSE if the specified rule does not exist or the command is passed
invalid arguments; otherwise, a multifield value is returned containing three values: the combined
sum of the matches for each pattern, the combined sum of partial matches, and the number of
activations.

Syntax

```
(matches <rule-name> [<verbosity>])
```

The <verbosity> argument is either the symbol verbose, succinct, or terse. If <verbosity> is not
specified or <verbosity> is verbose, then output will include details for each match, partial match,
and activation. If <verbosity> is succinct, then output will just include the total number of matches,
partial matches, and activations. If <verbosity> is terse, no output will be displayed.

Example

```
In this example, the example- 1 rule has three patterns and none are added by CLIPS. Fact f-
1 matches the first pattern, facts f-2 and f-3 match the the second pattern, and fact f-4 matches
the third pattern. Issuing the run command removes all of the rule’s activations from the
agenda.
```

```
CLIPS> (clear)
CLIPS>
(defrule example- 1
(a ?)
(b ?)
(c ?)
=>)
CLIPS> (assert (a 1) (b 1) (b 2) (c 1))
<Fact-4>
CLIPS> (facts)
f-1 (a 1)
f-2 (b 1)
f-3 (b 2)
f-4 (c 1)
```

CLIPS Basic Programming Guide 299

```
For a total of 4 facts.
CLIPS> (agenda)
0 example-1: f-1,f-2,f- 4
0 example-1: f-1,f-3,f- 4
For a total of 2 activations.
CLIPS> (run)
CLIPS> (agenda)
CLIPS>
```

```
The example- 2 rule has three patterns. There are no matches for the first pattern (since there
are no d facts), facts f-2 and f-3 match the third pattern, and fact f-4 matches the forth pattern.
```

```
CLIPS>
(defrule example- 2
(not (d ?))
(exists (b ?x)
(c ?x))
=>)
CLIPS> (agenda)
0 example-2: *,*
For a total of 1 activation.
CLIPS>
```

```
Listing the matches for the example- 1 rule displays the matches for the patterns indicated
previously. There are two partial matches which satisfy the first two patterns and two partial
matches which satisfy all three patterns. Since all of the rule’s activations were allowed to fire
there are none listed.
```

```
CLIPS> (matches example-1)
Matches for Pattern 1
f- 1
Matches for Pattern 2
f- 2
f- 3
Matches for Pattern 3
f- 4
Partial matches for CEs 1 - 2
f-1,f- 3
f-1,f- 2
Partial matches for CEs 1 - 3
f-1,f-2,f- 4
f-1,f-3,f- 4
Activations
None
(4 4 0)
CLIPS>
```

```
Listing the matches for the example- 2 rule displays the matches for the patterns indicated
previously. There is one partial match which satisfies the first two CEs (the not CE and the
exists CE). The symbol * indicates an existential match that is not associated with specific
```

```
300 Section 13: Commands
```

```
facts/instances (e.g. the not CE is satisfied because there are no d facts matching the pattern
so * is used to indicate a match as there’s no specific fact matching that pattern). Since none
of the rule’s activations were allowed to fire they are listed. The list of activations will always
be a subset of the partial matches for all of the rule’s CEs.
```

```
CLIPS> (matches example-2)
Matches for Pattern 1
None
Matches for Pattern 2
f- 2
f- 3
Matches for Pattern 3
f- 4
Partial matches for CEs 1 - 2
*,f- 2
*,f- 3
Partial matches for CEs 1 - 3
*,f-2,f- 4
Partial matches for CEs 1 (P1) , 2 (P2 - P3)
*,*
Activations
*,*
(3 4 1)
CLIPS>
```

```
To display a summary of the partial matches, specify the symbol succinct or terse as the
second argument to the matches command.
```

```
CLIPS> (matches example-2 succinct)
Pattern 1: 0
Pattern 2: 2
Pattern 3: 1
CEs 1 - 2: 2
CEs 1 - 3: 1
CEs 1 (P1) , 2 (P2 - P3): 1
Activations: 1
(3 4 1)
CLIPS> (matches example-2 terse)
(3 4 1)
CLIPS>
```

### 13.6.5 Setting a Breakpoint for a Rule

The set-break command sets a breakpoint for the specified defrule.

Syntax

```
(set-break <rule-name>)
```

```
CLIPS Basic Programming Guide 301
```

If a breakpoint is set for a rule, execution will halt prior to executing that rule. At least one rule
must fire before a breakpoint will stop execution. This command has no return value.

### 13.6.6 Removing a Breakpoint for a Rule

The remove-break command removes a breakpoint for the specified defrule.

Syntax

```
(remove-break [<defrule-name>])
```

If no argument is specified, then all breakpoints are removed. This command has no return value.

### 13.6.7 Displaying Rule Breakpoints

The show-breaks command displays all the rules which have breakpoints set. This command has
no return value.

Syntax

```
(show-breaks [<module-name>])
```

If the <module-name> argument is unspecified, then the names of all rules having breakpoints in
the current module are displayed. If <module-name> is specified, then the names of all rules having
breakpoints in the specified module are displayed. If <module-name> is the symbol \*, then the
names of all rules having breakpoints in all modules are displayed.

### 13.6.8 Refreshing a Rule

The refresh command places all current activations of the specified defrule on the agenda. This
command has no return value.

Syntax

```
(refresh <rule-name>)
```

### 13.6.9 Determining the Logical Dependencies of a Pattern Entity..................................

The dependencies command lists the partial matches from which a fact or instance receives logical
support. This command has no return value.

```
302 Section 13: Commands
```

Syntax

```
(dependencies <fact-or-instance-specifier>)
```

The <fact-or-instance-specifier> term includes variables bound on the LHS to fact-addresses or
instance-addresses, the fact-index of the desired fact (e.g. 3 for the fact labeled f-3), or the
instance-name (e.g. [car- 1 ]).

13.6.1 0 Determining the Logical Dependents of a Pattern Entity

The dependents command lists all facts and instances which receive logical support from a fact
or instance. This command has no return value.

Syntax

```
(dependents <fact-or-instance-specifier>)
```

The <fact-or-instance-specifier> term includes variables bound on the LHS to fact-addresses or
instance-addresses, the fact-index of the desired fact (e.g. 3 for the fact labeled f-3), or the
instance-name (e.g. [car- 1 ]).

## 13.7 Agenda Commands

The following commands manipulate the agenda.

### 13.7.1 Displaying the Agenda

The agenda command displays all activations on the agenda. This command has no return value.

Syntax

```
(agenda [<module-name>])
```

If the <module-name> argument is unspecified, then all activations in the current module (not the
current focus) are displayed. If <module-name> is specified, then all activations on the agenda of
the specified module are displayed. If <module-name> is the symbol \*, then the activations on all
agendas in all modules are displayed.

### 13.7.2 Running CLIPS

The run command starts execution of activated rules. If the optional first argument is a positive
integer, execution will cease after the specified number of rule firings or when the agenda contains
no rule activations. If there are no arguments or the first argument is a negative integer, execution

```
CLIPS Basic Programming Guide 303
```

will cease when the agenda contains no rule activations. If the focus stack is empty, then the MAIN
module automatically becomes the current focus. If the rules watch item is enabled using the
watch command, then an informational message will be printed each time a rule is fired. This
command has no return value.

Syntax

```
(run [<integer-expression>])
```

### 13.7.3 Focusing on a Group of Rules

The focus command pushes one or more modules onto the focus stack. The specified modules are
pushed onto the focus stack in the reverse order they are listed. The current module is set to the
last module pushed onto the focus stack. The current focus is the top module of the focus stack.
Thus (focus COLLECT PROCESS UPDATE) pushes UPDATE, then PROCESS, then COLLECT
unto the focus stack so that COLLECT is now the current focus. Note that the current focus is
different from the current module. Focusing on a module remembers the current module so that it
can be returned to later. Setting the current module with the set-current-module function changes
it without remembering the old module. Before a rule executes, the current module is changed to
the module in which the executing rule is defined (the current focus). This command returns the
symbol FALSE if an error occurs; otherwise it returns the symbol TRUE.

Syntax

```
(focus <module-name>+)
```

### 13.7.4 Stopping Rule Execution

The halt command stops execution of activated rules. After halt is called, control is returned from
the run command. The agenda is left intact, and execution may be continued with a run command.
This command has no return value.

Syntax

```
(halt)
```

### 13.7.5 Setting The Current Conflict Resolution Strategy

This set-strategy command sets the current conflict resolution strategy. The default strategy is
depth.

```
304 Section 13: Commands
```

Syntax

```
(set-strategy <strategy>)
```

The <strategy> argument must be one of the following symbols: depth, breadth, simplicity,
complexity, lex, mea, or random. The agenda will be reordered to reflect the new conflict
resolution strategy. The return value of this command is the prior conflict resolution strategy.

### 13.7.6 Getting The Current Conflict Resolution Strategy

The get-strategy command returns the current conflict resolution strategy (either the symbol
depth, breadth, simplicity, complexity, lex, mea, or random).

Syntax

```
(get-strategy)
```

### 13.7.7 Listing the Module Names on the Focus Stack

The list-focus-stack command lists all module names on the focus stack. The first name listed is
the current focus.

Syntax

```
(list-focus-stack)
```

### 13.7.8 Removing all Module Names from the Focus Stack

The clear-focus-stack command removes all module names from the focus stack.

Syntax

```
(clear-focus-stack)
```

### 13.7.9 Setting the Salience Evaluation Behavior

The set-salience-evaluation command sets the salience evaluation behavior. By default, salience
values are only evaluated when a rule is defined.

Syntax

```
(set-salience-evaluation <evaluation>)
```

```
CLIPS Basic Programming Guide 305
```

The <evaluation> argument must be one of the symbols when-defined, when-activated, or
every-cycle. The when-defined symbol forces salience evaluation at the time of rule definition.
The when-activated symbol forces salience evaluation at the time of rule definition and upon
being activated. The every-cycle symbol forces evaluation at the time of rule definition, upon
being activated, and after every rule firing. The return value of this command is the prior value for
salience evaluation.

### 13.7.10 Getting the Salience Evaluation Behavior

The get-salience-evaluation command returns the current salience evaluation behavior (either the
symbol when-defined, when-activated, or every-cycle).

Syntax

```
(get-salience-evaluation)
```

### 13.7.11 Refreshing the Salience Value of Rules on the Agenda

The refresh-agenda command reevaluates the saliences of all rules on the agenda regardless of
the current salience evaluation setting. This command has no return value.

Syntax

```
(refresh-agenda [<module-name>])
```

If the <module-name> argument is unspecified, then the agenda of the current module is refreshed.
If <module-name> is specified, then the agenda in the specified module is refreshed. If
<module-name> is the symbol \*, then the agenda in every module is refreshed.

## 13.8 Defglobal Commands

The following commands manipulate defglobals.

### 13.8.1 Displaying the Text of a Defglobal

The ppdefglobal command sends the source text of a defglobal to a logical name as output. If the
<logical-name> argument is t or unspecified, then output is sent to the logical name stdout,
otherwise it is sent to the specified logical name. If the logical name nil is used, then the text is
used as the return value of this command rather than being sent to an output destination; otherwise
this command has no return value.

```
306 Section 13: Commands
```

Unlike other constructs, defglobal definitions have no name associated with the entire construct.
The variable name passed to ppdefglobal should not include the question mark or the asterisks
(e.g. x is the variable name for the global variable ?_x_).

Syntax

```
(ppdefglobal <global-variable-name> [<logical-name>])
```

### 13.8.2 Displaying the List of Defglobals

The list-defglobals command displays the names of all defined defglobals. This command has no
return value.

Syntax

```
(list-defglobals [<module-name>])
```

If the <module-name> argument is unspecified, then the names of all defglobals in the current
module are displayed. If <module-name> is specified, then the names of all defglobals in the
specified module are displayed. If <module-name> is the symbol \*, then the names of all
defglobals in all modules are displayed.

### 13.8.3 Deleting a Defglobal

The undefglobal command deletes a previously defined defglobal.

Syntax

```
(undefglobal <defglobal-name>)
```

If the symbol _ is used for <defglobal-name>, then all defglobals will be deleted (unless there is a
defglobal named _). This command has no return value.

### 13.8.4 Displaying the Values of Global Variables

The show-defglobals command displays the name and current value of all defglobals. This
command has no return value.

Syntax

```
(show-defglobals [<module-name>])
```

If the <module-name> argument is unspecified, then the names and values of all defglobals in the
current module are displayed. If <module-name> is specified, then the names and values of all

```
CLIPS Basic Programming Guide 307
```

defglobals in the specified module are displayed. If <module-name> is the symbol \*, then the
names and values of all defglobals in all modules are displayed.

### 13.8.5 Setting the Reset Behavior of Global Variables

The set-reset-globals command sets the values of the reset globals behavior. When this behavior
is enabled (TRUE by default) global variables are reset to their original values when the reset
command is performed. The return value for this command is the old value for the behavior.

Syntax

```
(set-reset-globals <boolean-expression>)
```

### 13.8.6 Getting the Reset Behavior of Global Variables...................................................

The get-reset-globals command returns the current value of the reset global variables behavior
(either the symbol TRUE or FALSE).

Syntax

```
(get-reset-globals)
```

## 13.9 Deffunction Commands

The following commands manipulate deffunctions.

### 13.9.1 Displaying the Text of a Deffunction

The ppdeffunction command sends the source text of a deffunction to a logical name as output.
If the <logical-name> argument is t or unspecified, then output is sent to the logical name stdout,
otherwise it is sent to the specified logical name. If the logical name nil is used, then the text is
used as the return value of this command rather than being sent to an output destination; otherwise
this command has no return value.

Syntax

```
(ppdeffunction <deffunction-name> [<logical-name>])
```

### 13.9.2 Displaying the List of Deffunctions

The list-deffunctions command displays the names of all defined deffunctions. This command
has no return value.

```
308 Section 13: Commands
```

Syntax

```
(list-deffunctions)
```

### 13.9.3 Deleting a Deffunction

The undeffunction command deletes a previously defined deffunction.

Syntax

```
(undeffunction <deffunction-name>)
```

If the symbol _ is used for the <deffunction-name> argument, then all deffunctions will be deleted
(unless there exists a deffunction named _). This command has no return value.

## 13.10 Generic Function Commands

The following commands manipulate generic functions.

### 13.10.1 Displaying the Text of a Generic Function Header

The ppdefgeneric command sends the source text of a defgeneric to a logical name as output. If
the <logical-name> argument is t or unspecified, then output is sent to the logical name stdout,
otherwise it is sent to the specified logical name. If the logical name nil is used, then the text is
used as the return value of this command rather than being sent to an output destination; otherwise
this command has no return value.

Syntax

```
(ppdefgeneric <generic-function-name> [<logical-name>])
```

### 13.10.2 Displaying the Text of a Generic Function Method

The ppdefmethod command sends the source text of a defmethod to a logical name as output. If
the <logical-name> argument is t or unspecified, then output is sent to the logical name stdout,
otherwise it is sent to the specified logical name. If the logical name nil is used, then the text is
used as the return value of this command rather than being sent to an output destination; otherwise
this command has no return value.

Syntax

```
(ppdefmethod <generic-function-name> <index> [<logical-name>])
```

```
CLIPS Basic Programming Guide 309
```

The <index> term is the index of the method to be displayed. This command has no return value.

### 13.10.3 Displaying the List of Generic Functions

The list-defgenerics command displays the names of all defined generic functions.

Syntax

```
(list-defgenerics [<module-name>])
```

If the <module-name> argument is unspecified, then the names of all defgenerics in the current
module are displayed. If <module-name> is specified, then the names of all defgenerics in the
specified module are displayed. If <module-name> is the symbol \*, then the names of all
defgenerics in all modules are displayed. This command has no return value.

### 13.10.4 Displaying the List of Methods for a Generic Function

The list-defmethods command displays the names, arguments, and indices of all defined
defmethods. If no generic function name is specified, this command lists all defined generic
function methods. If a name is specified, then only the methods for the named generic function are
listed. The methods are listed in decreasing order of precedence for each generic function. This
command has no return value.

Syntax

```
(list-defmethods [<generic-function-name>])
```

### 13.10.5 Deleting a Generic Function

The undefgeneric command deletes a previously defined generic function.

Syntax

```
(undefgeneric <generic-function-name>)
```

If the symbol _ is used for the <generic-function-name> argument, then all generic functions will
be deleted (unless there exists a generic function called _). This command removes the header and
all methods for a generic function. This command has no return value.

```
310 Section 13: Commands
```

### 13.10.6 Deleting a Generic Function Method

The undefmethod command deletes a previously defined generic function method.

Syntax

```
(undefmethod <generic-function-name> <index>)
```

The <index> argument is the index of the method to be deleted for the generic function. If the
symbol _ is used for <index>, then all the methods for the generic function will be deleted. This is
different from the undefgeneric command because the header is not removed. If _ is used for
<generic-function-name>, then \* must also be specified for <index>, and all the methods for all
generic functions will be removed. This command removes the specified method for a generic
function, but even if the method removed is the last one, the generic function header is not
removed. This command has no return value.

### 13.10.7 Previewing a Generic Function Call

The preview-generic command lists all applicable methods for a particular generic function call
in order of decreasing precedence. The list-defmethods command is different in that it lists all
methods for a generic function.

Syntax

```
(preview-generic <generic-function-name> <expression>*)
```

This command does not actually execute any of the methods, but any side-effects of evaluating the
generic function arguments and any query parameter restrictions in methods do occur.

Example

```
CLIPS> (clear)
CLIPS> (defmethod + ((?a NUMBER) (?b INTEGER)))
CLIPS> (defmethod + ((?a INTEGER) (?b INTEGER)))
CLIPS> (defmethod + ((?a INTEGER) (?b NUMBER)))
CLIPS>
(defmethod + ((?a NUMBER) (?b NUMBER)
($?rest PRIMITIVE)))
CLIPS>
(defmethod + ((?a NUMBER)
(?b INTEGER (> ?b 2))))
CLIPS>
(defmethod + ((?a INTEGER (> ?a 2))
(?b INTEGER (> ?b 3))))
CLIPS>
(defmethod + ((?a INTEGER (> ?a 2))
(?b NUMBER)))
CLIPS> (preview-generic + 4 5)
```

```
CLIPS Basic Programming Guide 311
```

```
+ #7 (INTEGER <qry>) (INTEGER <qry>)
+ #8 (INTEGER <qry>) (NUMBER)
+ #3 (INTEGER) (INTEGER)
+ #4 (INTEGER) (NUMBER)
+ #6 (NUMBER) (INTEGER <qry>)
+ #2 (NUMBER) (INTEGER)
+ #SYS1 (NUMBER) (NUMBER) ($? NUMBER)
+ #5 (NUMBER) (NUMBER) ($? PRIMITIVE)
CLIPS>
```

## 13.11 Defclass Commands.....................................................................................................

The following commands manipulate defclasses.

### 13.11.1 Displaying the Text of a Defclass

The ppdefclass command sends the source text of a defclass to a logical name as output. If the
<logical-name> argument is t or unspecified, then output is sent to the logical name stdout,
otherwise it is sent to the specified logical name. If the logical name nil is used, then the text is
used as the return value of this command rather than being sent to an output destination; otherwise
this command has no return value.

Syntax

```
(ppdefclass <class-name> [<logical-name>])
```

### 13.11.2 Displaying the List of Defclasses

The list-defclasses command displays the names of all defined defclasses. If the <module-name>
argument is unspecified, then the names of all defclasses in the current module are displayed. If
<module-name> is specified, then the names of all defclasses in the specified module are
displayed. If <module-name> is the symbol \*, then the names of all defclasses in all modules are
displayed. This command has no return value.

Syntax

```
(list-defclasses [<module-name>])
```

### 13.11.3 Deleting a Defclass

The undefclass command deletes a previously defined defclass and all its subclasses.

```
312 Section 13: Commands
```

Syntax

```
(undefclass <class-name>)
```

If the symbol _ is used for the <class-name> argument, then all defclasses will be deleted (unless
there exists a defclass called _). This command has no return value.

### 13.11.4 Examining a Class...............................................................................................

The describe-class command provides a verbose description of a class including its role (whether
direct instances can be created or not), direct superclasses and subclasses, class precedence list,
slots with all their facets and sources, and all recognized message-handlers. This command has no
return value.

Syntax

```
(describe-class <class-name>)
```

Example

```
CLIPS> (clear)
CLIPS>
(defclass CHILD (is-a USER)
(role abstract)
(multislot parents (cardinality 2 2))
(slot age (type INTEGER)
(range 0 18))
(slot sex (access read-only)
(type SYMBOL)
(allowed-symbols male female)
(storage shared)))
CLIPS>
(defclass BOY (is-a CHILD)
(slot sex (source composite)
(default male)))
CLIPS>
(defmessage-handler BOY play ()
(println "The boy is now playing..."))
CLIPS> (describe-class CHILD)
================================================================================
********************************************************************************
Abstract: direct instances of this class cannot be created.
```

```
Direct Superclasses: USER
Inheritance Precedence: CHILD USER OBJECT
Direct Subclasses: BOY
--------------------------------------------------------------------------------
SLOTS : FLD DEF PRP ACC STO MCH SRC VIS CRT OVRD-MSG SOURCE(S)
parents : MLT STC INH RW LCL RCT EXC PRV RW put-parents CHILD
age : SGL STC INH RW LCL RCT EXC PRV RW put-age CHILD
sex : SGL STC INH R SHR RCT EXC PRV R NIL CHILD
```

```
CLIPS Basic Programming Guide 313
```

```
Constraint information for slots:
```

```
SLOTS : SYM STR INN INA EXA FTA INT FLT
parents : + + + + + + + + RNG:[-oo..+oo] CRD:[2..2]
age : + RNG:[0..18]
sex : #
--------------------------------------------------------------------------------
Recognized message-handlers:
init primary in class USER
delete primary in class USER
create primary in class USER
print primary in class USER
direct-modify primary in class USER
message-modify primary in class USER
direct-duplicate primary in class USER
message-duplicate primary in class USER
get-parents primary in class CHILD
put-parents primary in class CHILD
get-age primary in class CHILD
put-age primary in class CHILD
get-sex primary in class CHILD
********************************************************************************
================================================================================
CLIPS>
```

The following table explains the fields and their possible values in the slot descriptions.

```
314 Section 13: Commands
```

```
Field Values Explanation
FLD SGL/MLT Field type (single-field or multifield)
DEF STC/DYN/NIL Default value (static, dynamic, or none)
```

```
PRP INH/NIL Propagation to subclasses (inheritable or not inheritable)
```

```
ACC RW/R/INT Access (read-write, read-only, or initialize-only)
STO LCL/SHR Storage (local or shared)
MCH RCT/NIL Pattern-match (reactive or non-reactive)
SRC CMP/EXC Source type (composite or exclusive)
VIS PUB/PRV Visibility (public or private)
```

```
CRT R/W/RW/NIL Automatically created accessors (read, write, read-write, or none)
```

```
OVRD-MSG <message-name> Name of message sent for slotmake-instance, etc. - overrides in
```

```
SOURCE(S) <class-name>+ Source of slot (more than one class for composite)
```

In the constraint information summary for the slots, each of the columns shows one of the primitive
data types. A + in the column means that any value of that type is allowed in the slot. A # in the
column means that some values of that type are allowed in the slot. Range and cardinality
constraints are displayed to the far right of each slot’s row. The following table explains the
abbreviations used in the constraint information summary for the slots.

```
Abbreviation Explanation
SYM Symbol
STR String
INN Instance Name
INA Instance Address
EXA External Address
FTA Fact Address
INT Integer
FLT Float
RNG Range
CRD Cardinality
```

```
CLIPS Basic Programming Guide 315
```

### 13.11.5 Examining the Class Hierarchy

The browse-classes command provides a rudimentary display of the inheritance relationships
between a class and all its subclasses. Indentation indicates a subclass. Because of multiple
inheritance, some classes may appear more than once. Asterisks mark classes which are direct
subclasses of more than one class. With no arguments, this command starts with the root class
OBJECT. This command has no return value.

Syntax

```
(browse-classes [<class-name>])
```

Example

```
CLIPS> (clear)
CLIPS> (defclass A (is-a USER))
CLIPS> (defclass B (is-a USER))
CLIPS> (defclass C (is-a A B))
CLIPS> (defclass D (is-a USER))
CLIPS> (defclass E (is-a C D))
CLIPS> (defclass F (is-a E))
CLIPS> (browse-classes)
OBJECT
PRIMITIVE
NUMBER
INTEGER
FLOAT
LEXEME
SYMBOL
STRING
MULTIFIELD
ADDRESS
EXTERNAL-ADDRESS
FACT-ADDRESS
INSTANCE-ADDRESS *
INSTANCE
INSTANCE-ADDRESS *
INSTANCE-NAME
USER
A
C *
E *
F
B
C *
E *
F
D
E *
F
CLIPS>
```

```
316 Section 13: Commands
```

## 13.12 Message-handler Commands

The following commands manipulate defmessage-handlers.

### 13.12.1 Displaying the Text of a Defmessage-handler

The ppdefmessage-handler command sends the source text of a defmessage-handler to a logical
name as output. If the <logical-name> argument is t or unspecified, then output is sent to the
logical name stdout, otherwise it is sent to the specified logical name. If the logical name nil is
used, then the text is used as the return value of this command rather than being sent to an output
destination; otherwise this command has no return value.

Syntax

```
(ppdefmessage-handler <class-name> <handler-name>
[<handler-type> [<logical-name>]])
```

```
<handler-type> ::= around | before | primary | after
```

If the <handler-type> argument is not specified, it defaults to primary.

### 13.12.2 Displaying the List of Defmessage-handlers

The list-defmessage-handlers command displays the names of defined defmessage-handlers.

Syntax

```
(list-defmessage-handlers [<class-name> [inherit]])
```

If no arguments are specified, this command lists all defined message-handlers. If the optional
<class-name> argument is specified, this command lists all message-handlers for that class. In
addition, if the optional argument inherit is specified, inherited message-handlers are also listed.
This command has no return value.

### 13.12.3 Deleting a Defmessage-handler

The undefmessage-handler command deletes a previously defined message-handler.

Syntax

```
(undefmessage-handler <class-name> <handler-name>
[<handler-type>])
```

```
<handler-type> ::= around | before | primary | after
```

```
CLIPS Basic Programming Guide 317
```

If the <handler-type> argument is not specified, it defaults to primary. The symbol _ can be used
to specify a wildcard for any of the arguments (unless there is a class or message-handler named
_). This command has no return value.

### 13.12.4 Previewing a Message.........................................................................................

The preview-send command displays a list of all the applicable message-handlers for a message
sent to an instance of a particular class. The level of indentation indicates the number of times a
handler is shadowed, and lines connect the beginning and ending portions of the execution of a
handler if it encloses shadowed handlers. The right double-angle brackets indicate the beginning
of handler execution, and the left double-angle brackets indicate the end of handler execution.
Message arguments are not necessary for a preview since they do not dictate handler applicability.

Syntax

```
(preview-send <class-name> <message-name>)
```

Example

For the example in section 9.5.3, the output would be:

```
CLIPS> (preview-send USER my-message)
>> my-message around in class USER
| >> my-message around in class OBJECT
| | >> my-message before in class USER
| | << my-message before in class USER
| | >> my-message before in class OBJECT
| | << my-message before in class OBJECT
| | >> my-message primary in class USER
| | | >> my-message primary in class OBJECT
| | | << my-message primary in class OBJECT
| | << my-message primary in class USER
| | >> my-message after in class OBJECT
| | << my-message after in class OBJECT
| | >> my-message after in class USER
| | << my-message after in class USER
| << my-message around in class OBJECT
<< my-message around in class USER
CLIPS>
```

### 13.13 Definstances Commands

The following commands manipulate definstances.

```
318 Section 13: Commands
```

#### 13.13.1 Displaying the Text of a Definstances

The ppdefinstances command sends the source text of a definstances to a logical name as output.
If the <logical-name> argument is t or unspecified, then output is sent to the logical name stdout,
otherwise it is sent to the specified logical name. If the logical name nil is used, then the text is
used as the return value of this command rather than being sent to an output destination; otherwise
this command has no return value.

Syntax

```
(ppdefinstances <definstances-name> [<logical-name>])
```

13.13.2 Displaying the List of Definstances

The list-definstances command displays the names of all defined definstances.

Syntax

```
(list-definstances [<module-name>])
```

If the <module-name> argument is unspecified, then the names of all definstances in the current
module are displayed. If the <module-name> argument is specified, then the names of all
definstances in the specified module are displayed. If the <module-name> argument is the symbol
\*, then the names of all definstances in all modules are displayed. This command has no return
value.

#### 13.13.3 Deleting a Definstances

The undefinstances command deletes a previously defined definstances.

Syntax

```
(undefinstances <definstances-name>)
```

If the symbol _ is used for <definstances-name>, then all definstances will be deleted (unless there
exists a definstances called _). This command has no return value.

### 13.14 Instances Commands

The following commands manipulate instances of user-defined classes.

#### 13.14.1 Listing the Instances

The instances command lists existing instances.

```
CLIPS Basic Programming Guide 319
```

Syntax

```
(instances [<module-name> [<class-name> [inherit]]])
```

If no arguments are specified, all instances in scope of the current module are listed. If a module
name is given, all instances within the scope of that module are given. If the symbol _ is specified
(and there is no module named _), all instances in all modules are listed (only instances which
actually belong to classes of a module are listed for each module to prevent duplicates). If a class
name is specified, only the instances for the named class are listed. If a class is specified, then the
optional keyword inherit causes this command to list instances of subclasses of the class as well.
This command has no return value.

#### 13.14.2 Printing an Instance’s Slots from a Handler

The ppinstance command directly prints the slots of the active instance and is the one used to
implement the print handler attached to class USER. This command operates implicitly on the
active instance for a message, and thus can only be called from within the body of a
message-handler. This command has no return value.

Syntax

```
(ppinstance)
```

#### 13.14.3 Saving Instances to a Text File

The save-instances command saves all instances to the specified file using the following format.

```
(<instance-name> of <class-name> <slot-override>*)
```

```
<slot-override> ::= (<slot-name> <single-field-value>*)
```

A slot-override is generated for every slot of every instance, regardless of whether the slot currently
holds a default value or not. External-address and fact-address slot values are saved as strings.
Instance-address slot values are saved as instance-names. This command returns the number of
instances saved or -1 if an error occurs.

Syntax

```
(save-instances <file-name> [local | visible [[inherit] <class>+])
```

By default, save-instances saves only the instances of all defclasses in the current module.
Specifying visible saves instances for all classes within scope of the current module. Also,
particular classes may be specified for saving, but they must be in scope according to the local or
visible option. The inherit keyword can be used to force the saving of indirect instances of named

```
320 Section 13: Commands
```

classes as well (by default only direct instances are saved for named classes). Subclasses must still
be in local or visible scope in order for their instances to be saved. Unless the inherit option is
specified, only concrete classes can be specified. At least one class is required for the inherit
option.

The file generated by this command can be loaded by either the load-instances or
restore-instances command. The save-instances command does not preserve module
information, so the instance file should be loaded into the module which was current when it was
saved.

#### 13.14.4 Saving Instances to a Binary File........................................................................

The bsave-instances command works exactly like save-instances command except that the
instances are saved in a binary format which can only be loaded with the bload-instances
command. The advantage to this format is that loading binary instances can be much faster than
loading text instances for large numbers of instances. The disadvantage is that the file is not
portable to other platforms.

Syntax

```
(bsave-instances <file-name> [local | visible [[inherit] <class>+])
```

#### 13.14.5 Loading Instances from a Text File

The load-instances command loads instances in text format from a file and creates them. It can
read files created with the save-instances command or any UTF- 8 text file. Each instance should
be in the format described for the save-instances command (although the instance name can be
left unspecified). Calling load-instances is exactly equivalent to a series of make-instance calls.
This command returns the number of instances loaded or -1 if it could not access the instance file.

Syntax

```
(load-instances <file-name>)
```

#### 13.14.6 Loading Instances from a Text File without Message Passing

The restore-instances command loads instances from a file into the CLIPS environment. It can
read files created with save-instances or any UTF- 8 text file. Each instance should be in the format
described for the save-instances command (although the instance name can be left unspecified).
It is similar in operation to load-instances, however, unlike load-instances, restore-instances
does not use message-passing for deletions, initialization, or slot-overrides. Thus in order to
preserve object encapsulation, it is recommended that restore-instances only be used with files

```
CLIPS Basic Programming Guide 321
```

generated by save-instances. This command returns the number of instances loaded or -1 if it
could not access the instance file.

Syntax

```
(restore-instances <file-name>)
```

#### 13.14.7 Loading Instances from a Binary File

The bload-instances command is similar to restore-instances except that it can only work with
files generated by bsave-instances. This command returns the number of instances loaded or -1 if
it could not access the instance file.

Syntax

```
(bload-instances <file-name>)
```

### 13.15 Defmodule Commands

The following commands manipulate defmodule constructs.

#### 13.15.1 Displaying the Text of a Defmodule

The ppdefmodule command sends the source text of a defmodule to a logical name as output. If
the <logical-name> argument is t or unspecified, then output is sent to the logical name stdout,
otherwise it is sent to the specified logical name. If the logical name nil is used, then the text is
used as the return value of this command rather than being sent to an output destination; otherwise
this command has no return value.

Syntax

```
(ppdefmodule <defmodule-name> [<logical-name>])
```

#### 13.15.2 Displaying the List of Defmodules

The list-defmodules command displays the names of all defined defmodule constructs. This
command has no return value.

Syntax

```
(list-defmodules)
```

```
322 Section 13: Commands
```

### 13.16 Memory Management Commands

The following commands display CLIPS memory status information.

#### 13.16.1 Determining the Amount of Memory Used by CLIPS

The mem-used command returns an integer representing the number of bytes CLIPS has currently
in-use or cached for later use. This number does not include operating system overhead for
allocating memory.

Syntax

```
(mem-used)
```

#### 13.16.2 Determining the Number of Memory Requests Made by CLIPS

The mem-requests command returns an integer representing the number of outstanding memory
requests CLIPS has made from the operating system. If the operating system overhead for
allocating memory is known or guestimated, then the total memory used can be calculated with
the following formula.

```
(+ (mem-used) (* <overhead-in-bytes> (mem-requests)))
```

Syntax

```
(mem-requests)
```

#### 13.16.3 Releasing Memory Used by CLIPS

The release-mem command releases all free memory cached by CLIPS back to the operating
system. CLIPS will automatically call this command if it is running low on memory to allow the
operating system to coalesce smaller memory blocks into larger ones. This command returns an
integer representing the amount of memory freed to the operating system.

Syntax

```
(release-mem)
```

#### 13.16.4 Conserving Memory

The conserve-mem command is used to enable or disable the storage of the text representation for
constructs used by the save and pp<construct> commands. It should be called prior to loading
any constructs. This command has no return value.

```
CLIPS Basic Programming Guide 323
```

Syntax

```
(conserve-mem <value>)
```

The <value> argument should be the symbol on or off.

### 13.17 External Text Manipulation

CLIPS provides a set of functions to build and access a hierarchical lookup system for multiple
external files. Each file contains a set of text entries in a special format that CLIPS can later
reference and display. The basic concept is that CLIPS retains a map of the text file in memory
and can easily pull sections of text from the file without having to store the whole file in memory
and without having to sequentially search the file for the appropriate text.

#### 13.17.1 External Text File Format

Each external text file to be loaded into CLIPS must be described in a particular way. Each topic
entry in each file must be in the format shown following.

Syntax

```
<level-num> <entry-type> BEGIN-ENTRY- <topic-name>
```

-
- Topic information in form to be displayed when referenced.
-
- END-ENTRY

The delimiter strings (lines with BEGIN_ENTRY or END_ENTRY info) must be the only text on
their lines. Embedded white space between the fields of the delimiters is allowed.

The first parameter, <level-num>, is the level of the hierarchical tree to which the entry belongs.
The lower the number, the closer to the root level the topic is; i.e., the lowest level number indicates
the root level. Subtopics are indicated by making the level number of the current topic larger than
the previous entry (which is the parent). Thus, the tree must be entered in the file sequentially; i.e.,
a topic with all its subtopics must be described before going on to a topic at the same level. Entering
a number less than that of the previous topic will cause the tree to be searched upwards until a
level number is found which is less than the current one. The current topic then will be attached as
a subtopic at that level. In this manner, multiple root trees may be created. Level number and order
of entry in a file can indicate the order of precedence in which a list of subtopics that are all children
of the same topic will be searched. Topics with the same level number will be searched in the order
in which they appear in the file. Topics with lower-level numbers will be searched first.

```
324 Section 13: Commands
```

Example

```
0MBEGIN-ENTRY-ROOT
-- Text --
END-ENTRY
2IBEGIN-ENTRY-SUBTOPIC1
-- Text --
END-ENTRY
1IBEGIN-ENTRY-SUBTOPIC2
-- Text --
END-ENTRY
```

In the above example, SUBTOPIC1 and SUBTOPIC2 are children of ROOT. However, in
searching the children of ROOT, SUBTOPIC2 would be found first.

The second parameter in the format defined above, the <entry-type>, must be a single capital letter,
either M (for MENU) or I (for INFORMATION). Only MENU entries may have subtopics.

The third parameter defined above, the <topic-name>, can be any alphanumeric string of up to 80
characters. No white space can be embedded in the name.

Beginning a line with the delimiter “$$” forces the loader to treat the line as pure text, even if one
of the key delimiters is in it. When the line is printed, the dollar signs are treated as blanks.

Example

```
0MBEGIN-ENTRY-ROOT1
-- Root1 Text --
END-ENTRY
1MBEGIN-ENTRY-SUBTOPIC1
-- Subtopic1 Text --
END-ENTRY
2IBEGIN-ENTRY-SUBTOPIC4
-- Subtopic4 Text --
END-ENTRY
1IBEGIN-ENTRY-SUBTOPIC2
-- Subtopic2 Text --
END-ENTRY
0IBEGIN-ENTRY-ROOT2
-- Root2 Text --
END-ENTRY
```

- 1MBEGIN-ENTRY-ROOT3
  -- Root3 Text --
  END-ENTRY
  0IBEGIN-ENTRY-SUBTOPIC3
  -- Subtopic3 Text --
  END-ENTRY

Tree Diagram of Above Example :

```
CLIPS Basic Programming Guide 325
```

- > ROOT3 ---------> ROOT1 ---------> ROOT2
  > | / \
  > | / \
  > V V V
  > SUBTOPIC3 SUBTOPIC1 SUBTOPIC2
  > |
  > |
  > V
  > SUBTOPIC4

#### 13.17.2 Loading External Text

The fetch command loads the named file into the internal lookup table.

Syntax

```
(fetch <file-name>)
```

This command returns the number of entries loaded if the fetch succeeded. If the file could not be
loaded or was loaded already, this command returns the symbol FALSE.

#### 13.17.3 Printing External Text

The print-region command looks up a specified entry in a particular file which has been loaded
previously into the lookup table and prints the contents of that entry to the specified output.

Syntax

```
(print-region <logical-name> <file-name> <topic-field>*)
```

The <logical-name> argument is a name previously associated with an output destination. The
symbol t may be used as a shortcut for stdout. The <file-name> argument is the name of the
previously loaded file in which the entry is to be found. The optional <topic-field>\* arguments are
the full path of the topic entry to be found.

Each element or field in the path is delimited by white space, and the command is not case
sensitive. In addition, the entire name of a field does not need to be specified. Only enough
characters to distinguish the field from other choices at the same level of the tree are necessary. If
there is a conflict, the command will pick the first one in the list. A few special fields can be
specified.

```
^ Branch up one level.
```

```
326 Section 13: Commands
```

```
? When specified at the end of a path, this forces a display of the current menu, even on
branch-ups.
```

```
<nil> Giving no topic field will branch up one level.
```

The level of the tree for a file remains constant between calls to print-region. All levels count
only from the menu entry. Information levels do not count for branching up or down. To access an
entry at the root level after branching down several levels in a previous call or series of calls, an
equal number of branches up must be executed.

Examples

The following command displays the entry for ROOT SUBTOPIC from the file info.lis to standard
output.

```
(print-region t "info.lis" ROOT SUBTOPIC)
```

The following command will also produce the same output using fewer characters.

```
(print-region t "info.lis" roo sub)
```

Only one entry can be accessed per print-region call. This command returns the symbol TRUE
if the print-region call succeeded; otherwise, it returns the symbol FALSE.

```
CLIPS> (fetch "info.lis")
7
CLIPS> (print-region t "info.lis" roo sub)
```

```
-- Subtopic3 Text --
TRUE
CLIPS> (print-region t "info.lis" "?")
```

```
-- Root3 Text --
TRUE
CLIPS> (print-region t "info.lis" ^ root1 sub)
```

```
-- Subtopic1 Text --
TRUE
CLIPS> (print-region t "info.lis" sub)
```

```
-- Subtopic4 Text --
TRUE
CLIPS> (print-region t "info.lis" ^ subtopic2)
```

```
-- Subtopic2 Text --
TRUE
CLIPS> (print-region t "info.lis" ^ root2)
```

```
-- Root2 Text --
TRUE
```

```
CLIPS Basic Programming Guide 327
```

```
CLIPS> (toss "info.lis")
TRUE
CLIPS>
```

#### 13.17.4 Retrieving External Text

The get-region command looks up a specified entry in a particular file which has been loaded
previously into the lookup table and returns the contents of that entry as a string.

Syntax

```
(get-region <file-name> <topic-field>*)
```

The <file-name> argument is the name of the previously loaded file in which the entry is to be
found, and the optional <topic-field>\* arguments are the full path of the topic entry to be found.
The get-region the print-region commands share the same behavior for the special topic fields
and maintaining the level of the tree for a file between command calls. If an error occurs, this
command returns an empty string.

#### 13.17.5 Unloading an External Text File

The toss command unloads the named file from the internal lookup table and releases the memory
back to the system.

Syntax

```
(toss <file-name>)
```

This command returns the symbol TRUE if the toss succeeded; otherwise, it returns the symbol
FALSE.

### 13.18 Profiling Commands

The following commands provide the ability to profile CLIPS programs for performance.

#### 13.18.1 Setting the Profiling Report Threshold

The set-profile-percent-threshold command sets the minimum percentage of time that must be
spent executing a construct or user function for it to be displayed by the profile-info command.
By default, the percent threshold is zero, so all constructs or user-functions that were profiled and
executed at least once will be displayed by the profile-info command. The return value of this
command is the old percent threshold.

```
328 Section 13: Commands
```

Syntax

```
(set-profile-percent-threshold <number in the range 0 to 100>)
```

#### 13.18.2 Getting the Profiling Report Threshold

The get-profile-percent-threshold command returns the current value of the profile percent
threshold.

Syntax

```
(get-profile-percent-threshold)
```

#### 13.18.3 Resetting Profiling Information

The profile-reset command resets all profiling information currently collected for constructs and
user functions.

Syntax

```
(profile-reset)
```

#### 13.18.4 Displaying Profiling Information

The profile-info command displays profiling information currently collected for constructs or user
functions. Profiling information is displayed in six columns. The first column contains the name
of the construct or user function profiled. The second column indicates the number of times the
construct or user function was executed. The third column is the amount of time spent executing
the construct or user function. The fourth column is the percentage of time spent in the construct
or user function with respect to the total amount of time profiling was enabled. The fifth column
is the total amount of time spent in the first execution of the construct or user function and all
subsequent calls to other constructs/user functions. The sixth column is the percentage of this time
with respect to the total amount of time profiling was enabled.

Syntax

```
(profile-info)
```

#### 13.18.5 Profiling Constructs and User Functions

The profile command is used to enable/disable profiling of constructs and user functions. If
constructs are profiled, then the amount of time spent executing deffunctions, generic functions,
message handlers, and the RHS of defrules is tracked. If user-functions are profiled, then the time

```
CLIPS Basic Programming Guide 329
```

spent executing system and user defined functions is tracked. System defined functions include
predefined functions such as the < and numberp functions in addition to low level internal
functions which can not be directly called (these will usually appear in profile-info output in all
capital letters or surrounded by parentheses). It is not possible to profile constructs and user-
functions at the same time; enabling one disables the other. The off keyword argument disables
profiling. Profiling can be repeatedly enable and disabled as long as only one of constructs or
user-functions is consistently enabled. The total amount of time spent with profiling enabled will
be displayed by the profile-info command. If profiling is enabled from the command prompt, it is
a good idea to place the calls enabling and disabling profiling within a single progn function call.
This will prevent the elapsed profiling time from including the amount of time needed to type the
commands being profiled.

Syntax

```
(profile constructs | user-functions | off)
```

Example

```
CLIPS> (clear)
CLIPS> (deffacts start (fact 1))
CLIPS>
(deffunction function-1 (?x)
(bind ?y 1)
(loop-for-count (* ?x 100)
(bind ?y (+ ?y ?x))))
CLIPS>
(defrule rule- 1
?f <- (fact ?x&:(< ?x 100))
=>
(function-1 ?x)
(retract ?f)
(assert (fact (+ ?x 1))))
CLIPS> (reset)
CLIPS>
(progn (profile constructs)
(run)
(profile off))
CLIPS> (profile-info)
Profile elapsed time = 15.9657 seconds
```

```
Construct Name Entries Time % Time+Kids %+Kids
-------------- ------- ------ ----- --------- ------
```

```
*** Deffunctions ***
```

```
function- 1 99 0.154689 0.97% 0.154689 0.97%
```

```
*** Defrules ***
```

```
rule- 1 99 0.000212 0.00% 0.154902 0.97%
```

```
330 Section 13: Commands
```

CLIPS> (profile-reset)
CLIPS> (reset)
CLIPS>
(progn (profile user-functions)
(run)
(profile off))
CLIPS> (profile-info)
Profile elapsed time = 0.401675 seconds

```
Function Name Entries Time % Time+Kids %+Kids
------------- ------- ------ ----- --------- ------
retract 99 0.007953 0.07% 0.010646 0.09%
retract 99 0.000111 0.03% 0.000129 0.03%
assert 99 0.000185 0.05% 0.000275 0.07%
run 1 0.000124 0.03% 0.401674 100.00%
profile 1 0.000001 0.00% 0.000001 0.00%
* 99 0.000028 0.01% 0.000030 0.01%
+ 495099 0.124870 31.09% 0.187941 46.79%
< 99 0.000020 0.01% 0.000031 0.01%
progn 495198 0.059189 14.74% 0.401551 99.97%
loop-for-count 99 0.073839 18.38% 0.400954 99.82%
PCALL 99 0.000103 0.03% 0.401114 99.86%
FACT_PN_VAR3 99 0.000011 0.00% 0.000011 0.00%
FACT_JN_VAR1 99 0.000019 0.00% 0.000019 0.00%
FACT_JN_VAR3 198 0.000010 0.00% 0.000010 0.00%
FACT_STORE_MULTIFIELD 99 0.000031 0.01% 0.000059 0.01%
PROC_PARAM 495099 0.031070 7.74% 0.031070 7.74%
PROC_GET_BIND 495000 0.031995 7.97% 0.031995 7.97%
PROC_BIND 495099 0.080070 19.93% 0.267983 66.72%
CLIPS> (set-profile-percent-threshold 1)
0.0
CLIPS> (profile-info)
Profile elapsed time = 12.0454 seconds
```

```
Function Name Entries Time % Time+Kids %+Kids
------------- ------- ------ ----- --------- ------
+ 49599 3.626217 30.10% 5.765490 47.86%
+ 495099 0.124870 31.09% 0.187941 46.79%
progn 495198 0.059189 14.74% 0.401551 99.97%
loop-for-count 99 0.073839 18.38% 0.400954 99.82%
PROC_PARAM 495099 0.031070 7.74% 0.031070 7.74%
PROC_GET_BIND 495000 0.031995 7.97% 0.031995 7.97%
PROC_BIND 495099 0.080070 19.93% 0.267983 66.72%
CLIPS> (profile-reset)
CLIPS> (profile-info)
CLIPS>
```

```
CLIPS Basic Programming Guide 331
```

## Appendix A: Support Information

### A.1 Questions and Information

The URL for the CLIPS Web page is clipsrules.net.

Questions regarding CLIPS can be posted to one of several online forums including the CLIPS
Expert System Group, groups.google.com/group/CLIPSESG/, the SourceForge CLIPS Forums,
sourceforge.net/forum/?group_id=215471, and Stack Overflow,
stackoverflow.com/questions/tagged/clips.

Inquiries related to the use or installation of CLIPS can be sent via electronic mail to
support@clipsrules.net.

### A.2 Documentation

The CLIPS Reference Manuals and other documentation are available at
clipsrules.net/Documentation.html.

Adventures in Rule-Based Programming is a fun introduction to writing applications using CLIPS.
In this tutorial you’ll learn the basic concepts of rule-based programming, where rules are used to
specify the logic of what must be accomplished, but an inference engine determines when rules
are applied. You’ll incrementally create a fully functional text adventure game, and in the process,
learn how to write, organize, debug, test, and deploy CLIPS code. Visit clipsrules.net/airbp for
more information.

Expert Systems: Principles and Programming, 4th Edition, by Giarratano and Riley comes with a
CD-ROM containing CLIPS 6.22 executables (DOS, Windows XP, and Mac OS), documentation,
and source code. The first half of the book is theory oriented and the second half covers rule-based,
procedural, and object-oriented programming using CLIPS.

### A.3 CLIPS Source Code and Executables

CLIPS executables and source code are available on the SourceForge web site at
sourceforge.net/projects/clipsrules/files.

```
332 Appendix B: Update Release Notes
```

## Appendix B: Update Release Notes

The following changes were introduced in version 6.4 of CLIPS.

- Initial Fact – The initial-fact deftemplate and deffacts are no longer supported.
- Initial Object – The INITIAL-OBJECT defclass and initial-object definstances are no longer
  supported.
- Object Pattern Performance Improvements – Rule performance has been improved for
  object patterns particularly in situations with a large number of class slots.
- New Functions and Commands - Several new functions and commands have been added.
  They are:
  - str-replace (see section 12.3.13)
  - print (see section 12.4. 3 )
  - println (see section 12.4. 3 )
  - unget-char (see section 12.4.10)
  - flush (see section 12.4. 13 )
  - rewind (see section 12.4. 14 )
  - tell (see section 12.4. 15 )
  - seek (see section 12.4. 16 )
  - chdir (see section 12.4.17)
  - atan2 (see section 12.5.11.1)
  - local-time (see section 12.7.12)
  - gm-time (see section 12.7.13)
  - get-error (see section 12.7.1 4 )
  - clear-error (see section 12.7.1 5 )

CLIPS Basic Programming Guide 333

- set-error (see section 12.7.1 6 )
- void (see section 12.7.17)
- bsave-facts (see section 13.4.4)
- bload-facts (see section 1 3. 4. 6 )
- Command and Function Changes - The following commands and functions have been
  changed:
- assert (see section 12.9.1). When a duplicate fact is asserted, the return value of the assert
  command is the originally asserted fact. The symbol false is only returned by the assert
  command if an error occurs.
- bsave-instances (see section 13.14.3). The bsave-instances function now returns -1 if an
  error occurs.
- duplicate (see section 12.9. 4 ). The return value of a function call can be used to specify
  the fact being duplicated. Specifying the fact using a fact-index is no longer limited to top-
  level commands.
- eval (see section 12.3.5). When executed from the command prompt, the eval function
  can access previously bound local variables. The eval function is now available in binary-
  load only and run-time CLIPS configurations.
- explode$ (see section 12. 2. 6 ). The explode$ function now returns symbols for tokens
  that are not primitive values.
- funcall (see section 12.7.9). A module specifier can be used as part of the function name
  when referencing a deffunction or defgeneric that is exported by a module.
- open (see section 12.4.1). The r+, w+, and a+ modes and their binary counterparts are
  now supported.
- length$ (see section 12.2.13). The length$ function no longer accepts strings or symbols
  as arguments.
- load (see section 13.1.1). The file name and line number are now printed for each
  error/warning message generated during execution of this command.
- load-facts (see section 13.4. 5 ). The load-facts command now returns the number of facts
  loaded.

334 Appendix B: Update Release Notes

- modify (see section 12.9.3). The modify command now preserves the fact-index and fact-
  address of the fact being modified. Modifying a fact without changing any slots no longer
  retracts and reasserts the original fact. If facts are being watched, only changed slots are
  displayed when a fact is being modified. The return value of a function call can be used
  to specify the fact being modified. Specifying the fact using a fact-index is no longer
  limited to top-level commands. If all slot changes specified in the modify command match
  the current values of the fact to be modified, no action is taken.
- pointerp. The pointerp function is deprecated. The external-addressp function (see
  section 12.1.10) should be used instead.
- Pretty Print Commands – The ppdefclass, ppdeffacts, ppdeffunction, ppdefgeneric,
  ppdefglobal, ppdefinstances, ppdefmessage-handler, ppdefmethod, ppdefmodule,
  ppdefrule, and ppdeftemplate commands now accept an optional logical name
  argument. The logical name nil can be used to return the source text as the command
  return value rather than sending it to an output destination. The ppfact command now
  returns the source text of a fact when the logical name nil is specified.
- read (see section 12.4.4). The read function now returns symbols for tokens that are not
  primitive values. For example, the token ?var is returned as the symbol ?var and not the
  string "?var". If an error occurs, the read function now returns the symbol FALSE and the
  get-error function can be used to determine the error that occurred.
- readline (see section 12.4. 5 ). If an error occurs, the readline function now returns the
  symbol FALSE.
- read-number (see section 12.4. 11 ). If an error occurs, the read-number function now
  returns the symbol FALSE.
- round (see section 12.5.22). If the argument to the round function is exactly between two
  integers, it is now rounded away from zero.
- save-facts (see section 13.4. 3 ). The save-facts command now returns the number of facts
  saved.
- save-instances (see section 13.14.3). The save-instances function now returns -1 if an
  error occurs.
- system (see section 13.1.12). The system function now returns an integer completion
  status.
- str-index (see section 12.3.4). The str-index function now returns 1 if the search string is
  the empty string "".

CLIPS Basic Programming Guide 335

- string-to-field (see section 12. 3. 12 ). The string-to-field function now returns symbols
  for tokens that are not primitive values.
- watch (see section 13.2.3). The compilations watch flag now defaults to off.
- Incremental Reset – This behavior is now always enabled—newly defined rules are always
  updated based upon the current state of the fact-list. The get-incremental-reset and set-
  incremental-reset functions are no longer supported.
- Static Constraint Checking – This behavior is now always enabled—constraint violations
  are always checked when function calls and constructs are parsed. The get-static-constraint-
  checking and set-static-constraint-checking functions are no longer supported.
- Auto Float Dividend – This behavior is now always enabled— the dividend of the division
  function is always automatically converted to a floating point number. The get-auto-float-
  dividend and set-auto-float-dividend functions are no longer supported.
- Legacy Functions – The direct-mv-delete, direct-mv-insert, direct-mv-replace, length,
  member, mv-append, mv-delete, mv-replace, mv-slot-delete, mv-slot-insert, mv-slot-
  replace, mv-subseq, nth, sequencep, str-explode, str-implode, subset, and wordp
  functions are no longer supported.
- Fact Query Pruning – The fact set query functions (see section 12.9.12) now prune all fact
  sets containing facts retracted by actions applied to prior fact sets.
- Instance Query Pruning – The instance set query functions (see sections 9.7) now prune all
  instance sets containing instances deleted by actions applied to prior instance sets.
- Retracted Fact Errors – The following functions now generate errors when used with
  retracted facts: dependencies, dependents, duplicate, fact-index, fact-relation, fact-slot-
  names, fact-slot-value, modify, ppfact, and timetag.
- Logical Names – The wclips, wdialog, wdisplay, and wtrace logical names are no longer
  supported. Output previously directed to these logical names is now sent to stdout.
- Single Slot Keyword – The single-slot keyword in defclass definitions is no longer
  supported. The slot keyword should be used in its place.

The following changes were introduced in version 6.4.1 of CLIPS.

- New Functions and Commands - Several new functions and commands have been added.
  They are:
  - union$ (see section 12.2.16)

336 Appendix B: Update Release Notes

- intersection$ (see section 12.2.17)
- difference$ (see section 12.2.18)

```
CLIPS Basic Programming Guide 337
```

## Appendix C: Glossary...............................................................................................................

This section defines some of the terminology used throughout this manual.

```
abstraction The definition of new classes to describe the common properties
and behavior of a group of objects.
```

```
action A function executed by a construct (such as the RHS of a rule)
which typically has no return value, but performs some useful
action.
```

```
activation A rule is activated if all of its conditional elements are satisfied and
it has not yet fired based on a specific set of matching facts and/or
instances that caused it to be activated. Note that a rule can be
activated by more than one set of facts and/or instances. An
activated rule that is placed on the agenda is called an activation.
```

```
active instance The object responding to a message which can be referred to by
?self in the message’s handlers.
```

```
agenda A list of all rules that are presently ready to fire. It is sorted by
salience values and the current conflict resolution strategy. The rule
at the top of the agenda is the next rule that will fire.
```

```
antecedent The LHS of a rule.
```

```
bind The action of storing a value in a variable.
```

```
class Template for describing the common properties (slots) and
behavior (message-handlers) of a group of objects called instances
of the class.
```

```
class precedence list A linear ordering of classes which describes the path of inheritance
for a class.
```

```
command A function executed at the REPL (such as the reset command)
typically having no return value.
```

338 Appendix C: Glossary

command prompt In the interactive interface, the “CLIPS>” prompt which indicates
that CLIPS is ready for a command to be entered.

condition A conditional element.

conditional
element

```
A restriction on the LHS of a rule which must be satisfied in order
for the rule to be applicable (also referred to as a CE).
```

conflict resolution
strategy

```
A method for determining the order in which rules should fire
among rules with the same salience. There are seven different
conflict resolution strategies: depth, breadth, simplicity,
complexity, lex, mea, and random.
```

consequent The RHS of a rule.

constant A non-varying single field value directly expressed as a series of
characters.

constraint In patterns, a constraint is a requirement that is placed on the value
of a field from a fact or instance that must be satisified in order for
the pattern to be satisfied. For example, the ~red constraint is
satisfied if the field to which the constraint is applied is not the
symbol red. The term constraint is also used to refer to the legal
values allowed in the slots of facts and instances.

construct A high level CLIPS abstraction used to add components to the
knowledge base.

current focus The module from which activations are selected to be fired.

current module The module to which newly defined constructs that do not have a
module specifier are added. It is also the default module for certain
commands which accept as an optional argument a module name
(such as list-defrules).

daemon A message-handler which executes implicitly whenever some
action is taken upon an object, such as initialization, deletion, or
slot access.

deffunction A non-overloaded function written directly in CLIPS.

CLIPS Basic Programming Guide 339

deftemplate fact A deftemplate name followed by a list of named fields (slots) and
specific values used to represent a deftemplate object. Note that a
deftemplate fact has no inheritance. Also called a non-ordered fact.

deftemplate pattern A list of named constraints (constrained slots). A deftemplate
pattern describes the attributes and associated values of a
deftemplate object. Also called a non-ordered pattern.

delimiter A character which indicates the end of a symbol. The following
characters act as delimiters: any non-printable ASCII character
(including spaces, tabs, carriage returns, and line feeds), a double
quote, opening and closing parenthesis “(” and “)”, an ampersand
“&”, a vertical bar “|”, a less than “<”, a semicolon “;”, and a tilde
“~”.

dynamic binding The deferral of which message-handlers will be called for a
message until run-time.

encapsulation The requirement that all manipulation of instances of user-defined
classes be done with messages.

expression A function call with arguments specified.

external-address The address of an external data structure returned by a function
(written in a language such as C) that has been integrated with
CLIPS.

external function A function written in an external language (such as C) defined by
the user or provided by CLIPS and called from within CLIPS rules.

facet A component of a slot specification for a class, e.g. default value
and cardinality.

fact An ordered or deftemplate (non-ordered) fact. Facts are the data
about which rules reason and represent the current state of the
program.

fact-address A pointer to a fact obtained by binding a variable to the fact which
matches a pattern on the LHS of a rule.

340 Appendix C: Glossary

fact-identifier A shorthand notation for referring to a fact. It consists of the
character “f”, followed by a dash, followed by the fact-index of the
fact.

fact-index A unique integer index used to identify a particular fact.

fact-list The list of current facts.

field A placeholder (named or unnamed) that has a value.

fire A rule is said to have fired if all of its conditions are satisfied and
the actions then are executed.

float A number that begins with an optional sign followed optionally in
order by zero or more digits, a decimal point, zero or more digits,
and an exponent (consisting of an e or E followed by an integer). A
floating point number must have at least one digit in it (not
including the exponent) and must either contain a decimal point or
an exponent.

focus As a verb, refers to changing the current focus. As a noun, refers to
the current focus.

focus stack The list of modules that have been focused upon. The module at the
top of the focus stack is the current focus. When all the activations
from the current focus have been fired, the current focus is removed
from the focus stack and the next module on the stack becomes the
current focus.

function A piece of executable code identified by a specific name which
returns a useful value or performs a useful side effect. Typically
only used to refer to functions which do return a value (whereas
commands and actions are used to refer to functions which do not
return a value).

generic dispatch The process whereby applicable methods are selected and executed
for a particular generic function call.

generic function A function written in CLIPS which can do different things
depending on what the number and types of its arguments.

CLIPS Basic Programming Guide 341

inference engine The mechanism that automatically matches patterns against the
current state of the fact-list and list of instances and determines
which rules are applicable.

inheritance The process whereby one class can be defined in terms of other
class(es).

instance An object is an instance of a class. Throughout the documentation,
the term instance usually refers to objects which are instances of
user-defined classes.

instance (of a
user-defined class)

```
An object which can only be manipulated via messages, i.e all
objects except symbols, strings, integers, floats, multifields and
external-addresses.
```

instance-address The address of an instance of a user-defined class.

instance-name A symbol enclosed within left and right brackets. An instance-name
refers to an object of the specified name which is an instance of a
user-defined class.

instance-set An ordered collection of instances of user-defined classes. Each
member of an instance-set is an instance of a set of classes, where
the set can be different for each member.

instance-set distributed
action

```
A user-defined expression which is evaluated for every instance-set
which satisfies an instance-set query.
```

instance-set query A user-defined boolean expression applied to an instance-set to see
if it satisfies further user-defined criteria.

integer A number that begins with an optional sign followed by one or more
digits.

LHS Left-Hand Side. The set of conditional elements that must be
satisfied for the actions of the RHS of a rule to be performed.

list A group of items with no implied order.

logical name A symbolic name that is associated with an I/O source or
destination.

342 Appendix C: Glossary

message The mechanism used to manipulate an object.

message dispatch The process whereby applicable message-handlers are selected and
executed for a particular message.

message-handler An implementation of a message for a particular class of objects.

message-handler
precedence

```
The property used by the message dispatch to select between
handlers when more than one is applicable to a particular message.
```

method An implementation of a generic function for a particular set of
argument restrictions.

method index A shorthand notation for referring to a method with a particular set
of parameter restrictions.

method precedence The property used by the generic dispatch to select a method when
more than one is applicable to a particular generic function call.

module A container where a set of constructs can be grouped together such
that explicit control can be maintained over restricting the access of
the constructs by other modules. Also used to control the flow of
execution of rules through the use of the focus command.

module specifier A notation for specifying a module. It consists of a module name
followed by two colons. When placed before a construct name, it’s
used to specify which module a newly defined construct is to be
added to or to specify which construct a command will affect if that
construct is not in the current module.

multifield A sequence of unnamed placeholders each having a value.

multifield value A sequence of zero or more single-field values.

non-ordered fact A deftemplate fact.

number An integer or float.

object A symbol, a string, a floating-point or integer number, a multifield
value, an external address, or an instance of a user-defined class.

order Position is significant.

CLIPS Basic Programming Guide 343

ordered fact A sequence of unnamed fields.

ordered pattern A sequence of constraints.

overload The process whereby a generic function can do different things
depending on the types and number of its arguments, i.e. the generic
function has multiple methods.

pattern A conditional element on the LHS of a rule which is used to match
facts in the fact-list.

pattern entity An item that is capable of matching a pattern on the LHS of a rule.
Facts and instances are the only types of pattern entities available.

pattern-matching The process of matching facts or instances to patterns on the LHS
of rules.

polymorphism The ability of different objects to respond to the same message in a
specialized manner.

primitive type object A symbol, string, integer, float, multifield, fact address, instance
name, instance address, or external-address.

Relation The first field in a fact or fact pattern. Synonomous with the
associated deftemplate name.

REPL Read-Eval-Print Loop. The primary method for issuing commands
to CLIPS interactively.

RHS Right-Hand Side. The actions to be performed when the LHS of a
rule is satisfied.

rule A collection of conditions and actions. When all patterns are
satisfied, the actions will be taken.

salience A priority number given to a rule. When multiple rules are ready
for firing, they are fired in order of priority. The default salience is
zero (0). Rules with the same salience are fired according to the
current conflict resolution strategy.

sequence An ordered list.

344 Appendix C: Glossary

shadowed
message-handler

```
A message-handler that must be explicitly called by another
message-handler in order to execute.
```

shadowed method A method that must be explicitly called by another method in order
to execute.

single-field value One of the primitive data types: float, integer, symbol, string,
external-address, instance-name, or instance-address.

slot Named single-field or multifield. To write a slot give the field name
(attribute) followed by the field value. A single-field slot has one
value, while a multifield slot has zero or more values. Note that a
multifield slot with one value is strictly not the same as a single
field slot. However, the value of a single-field slot (or variable) may
match a multifield slot (or multifield variable) that has one field.

slot-accessor Implicit message-handlers which provide read and write access to
slots of an object.

specificity (class) A class that precedes another class in a class precedence list is said
to be more specific. A class is more specific than any of its
superclasses.

specificity (rule) A measure of how “specific” the LHS of a rule is in the
pattern-matching process. The specificity is determined by the
number of constants, variables, and function calls used within LHS
conditional elements.

string A set of characters that starts with double quotes (") and is followed
by zero or more printable characters and ends with double quotes.

subclass If a class inherits from a second class, the first class is a subclass of
the second class.

superclass If a class inherits from a second class, the second class is a
superclass of the first class.

symbol Any sequence of characters that starts with any printable ASCII
character and is followed by zero or more characters.

top-level In the interactive interface, the “CLIPS>” prompt which indicates
that CLIPS is ready for a command to be entered.

CLIPS Basic Programming Guide 345

value A single or multifield value.

variable An symbolic location which can store a value.

```
346 Appendix D: Performance Considerations
```

## Appendix D: Performance Considerations

This appendix explains various techniques that the user can apply to a CLIPS program to maximize
performance. Included are discussions of pattern ordering in rules, use of deffunctions in lieu of
non-overloaded generic functions, parameter restriction ordering in generic function methods, and
various approaches to improving the speed of message-passing and reading slots of instances.

### D.1 Ordering of Patterns on the LHS.....................................................................................

The issues which affect performance of a rule-based system are considerably different from those
which affect conventional programs. This section discusses the single most important issue: the
ordering of patterns on the LHS of a rule.

CLIPS is a rule language based on the RETE algorithm which was designed to provide very
efficient pattern-matching. In optimizing rules, it is beneficial to have some understanding of how
the pattern-matcher works.

Prior to initiating execution, each rule is loaded and a network of all patterns that appear on the
LHS of any rule is constructed. As facts and instances of reactive classes (referred to collectively
as pattern entities) are created, they are filtered through the pattern network. If the pattern entities
match any of the patterns in the network, the rules associated with those patterns are partially
instantiated. When pattern entities exist that match multiple sequential patterns on the LHS of the
rule beginning with the first pattern, variable bindings (if any) across patterns are considered. They
are considered from the top to the bottom; i.e., the first pattern on the LHS of a rule is considered,
then the second, and so on. If the variable bindings for all patterns are consistent with the
constraints applied to the variables, the rules are activated and placed on the agenda.

This is a very simple description of what occurs in CLIPS, but it gives the basic idea. A number
of important considerations come out of this. Basic pattern-matching is done by filtering through
the pattern network. The time involved in doing this is fairly constant. The slow portion of basic
pattern-matching comes from comparing variable bindings across patterns. Therefore, the single
most important performance factor is the ordering of patterns on the LHS of the rule.
Unfortunately, there are no hard and fast methods that will always order the patterns properly.
There are a few general rules for ordering the patterns.

```
1) Most specific to most general. The more wildcards or unbound variables there are in a pattern,
the lower it should go. If the rule firing can be controlled by a single pattern, place that pattern
first. This technique often is used to provide control structure in an expert system; e.g., some
kind of “phase” fact. Putting this kind of pattern first will guarantee that the rest of the rule
```

```
CLIPS Basic Programming Guide 347
```

```
will not be considered until that pattern exists. This is most effective if the single pattern
consists only of literal constraints. If multiple patterns with variable bindings control rule
firing, arrange the patterns so the most important variables are bound first and compared as
soon as possible to the other pattern constraints. The use of phase facts is not recommended
for large programs if they are used solely for controlling the flow of execution (use
defmodules instead).
```

```
2) Patterns with the lowest number of occurrences in the fact-list or instance-list should go near
the top. A large number of patterns of a particular form in the fact-list or instance-list can
cause numerous partial instantiations of a rule that have to be eliminated by comparing the
variable bindings, a slower operation.
```

```
3) Volatile patterns (ones that are retracted and asserted continuously) should go last, particularly
if the rest of the patterns are mostly independent. Every time a pattern entity is created, it must
be filtered through the network. If a pattern entity causes a partial rule instantiation, the
variable bindings must be considered. By putting volatile patterns last, the variable bindings
only will be checked if all of the rest of the patterns already exist.
```

These rules are not independent and commonly conflict with each other. At best, they provide
some rough guidelines. Since all systems have these characteristics in different proportions, at a
glance the most efficient manner of ordering patterns for a given system is not evident. The best
approach is to develop the rules with some consideration of ordering, but delay optimization until
later in development.

### D.2 Deffunctions versus Generic Functions

Deffunctions execute more quickly than generic function because generic functions must first
examine their arguments to determine which methods are applicable. If a generic function has only
one method, a deffunction probably would be better. Care should be taken when determining if a
particular function truly needs to be overloaded. In addition, if recompiling and relinking CLIPS
is not prohibitive, user-defined external functions are even more efficient than deffunctions. This
is because deffunction are interpreted whereas external functions are directly executed.

### D.3 Ordering of Method Parameter Restrictions

When the generic dispatch examines a generic function’s method to determine if it is applicable to
a particular set of arguments, it examines that method’s parameter restrictions from left to right.
The programmer can take advantage of this by placing parameter restrictions which are less
frequently satisfied than others first in the list. Thus, the generic dispatch can conclude as quickly
as possible when a method is not applicable to a generic function call. If a group of restrictions are
all equally likely to be satisfied, placing the simpler restrictions first, such as those without queries,
will also allow the generic dispatch to conclude more quickly for a method that is not applicable.

```
348 Appendix D: Performance Considerations
```

### D.4 Instance-Addresses versus Instance-Names....................................................................

COOL allows instances of user-defined classes to be referenced either by address or by name in
functions which manipulate instances, such as message-passing with the send function. However,
when an instance is referenced by name, CLIPS must perform an internal lookup to find the
instance-address anyway. If the same instance is going to be manipulated many times, it might be
advantageous to store the instance-address and use that as a reference. This will allow CLIPS to
always go directly to the instance.

### D.5 Reading Instance Slots Directly

Normally, message-passing must be used to read or set a slot of an instance. However, slots can
be read directly within instance-set queries and message-handlers, and they can be set directly
within message-handlers. Accessing slots directly is significantly faster than message-passing.
Unless message-passing is required (because of slot daemons), direct access should be used when
allowed.

```
CLIPS Basic Programming Guide 349
```

## Appendix E: CLIPS Warning Messages

CLIPS typically will display two kinds of warning messages: those associated with executing
constructs and those associated with loading constructs. This appendix describes some of the more
common warning messages and what they mean. Each message begins with a unique identifier
enclosed in brackets followed by the keyword WARNING; the messages are listed here in
alphabetic order according to the identifier.

[CSTRCPSR1] WARNING: Redefining <constructType>: <constructName>
or
[CSTRCPSR1] WARNING: Method # <method index> redefined.
This indicates that a previously defined construct of the specified type has been redefined.

[CSTRNBIN1] WARNING: Constraints are not saved with a binary image when dynamic
constraint checking is disabled
or
[CSTRNCMP1] WARNING: Constraints are not saved with a constructs-to-c image when
dynamic constraint checking is disabled
These warnings occur when dynamic constraint checking is disabled and the constructs-to-c or
bsave commands are executed. Constraints attached to deftemplate and defclass slots will not be
saved with the runtime or binary image in these cases since it is assumed that dynamic constraint
checking is not required. Enable dynamic constraint checking with the
set-dynamic-constraint-checking function before calling constructs-to-c or bsave in order to
include constraints in the runtime or binary image.

[DFFNXFUN1] WARNING: Deffunction <name> only partially deleted due to usage by
other constructs.
During a clear or deletion of all deffunctions, only the actions of a deffunction were deleted
because another construct which also could not be deleted referenced the deffunction.

Example:
CLIPS>
(deffunction hello ()
(println "Hi there!"))
CLIPS>
(deffunction delete ()
(hello)
(undeffunction \*))
CLIPS> (delete)7yuo

```
350 Appendix E: CLIPS Warning Messages
```

[GENRCBIN1] WARNING: COOL not installed! User-defined class in method restriction
substituted with OBJECT.
This warning occurs when a generic function method restricted by defclasses is loaded using the
bload command into a CLIPS configuration where the object language is not enabled. The
restriction containing the defclass will match any of the primitive types.

[PRCCODE4] WARNING: Execution halted during the actions of defrule <name>.
This warning occurs when the rules are being watch and rule execution is halted.

Example:
CLIPS> (defrule halt => (halt))
CLIPS> (watch rules)
CLIPS> (run)

[SCANNER1] WARNING: Over or underflow of long long integer.
This warning occurs when an integer is outside of the range of values that can be represented in
the C long long integer type.

Example:
CLIPS> 12345678901234567890

```
CLIPS Basic Programming Guide 351
```

## Appendix F: CLIPS Error Messages

CLIPS typically will display two kinds of error messages: those associated with executing
constructs and those associated with loading constructs. This appendix describes some of the more
common error messages and what they mean. Each message begins with a unique identifier
enclosed in brackets; the messages are listed here in alphabetic order according to the identifier.

[ANALYSIS1] Duplicate pattern-address <variable name> found in CE <CE number>.
This message occurs when two facts or instances are bound to the same pattern-address variable.

Example:
CLIPS> (defrule error ?f <- (a) ?f <- (b) =>)

[ANALYSIS2] Pattern-address <variable name> used in CE #2 was previously bound
within a pattern CE.
A variable first bound within a pattern cannot be later bound to a fact-address.

Example:
CLIPS> (defrule error (a ?f) ?f <- (b) =>)

[ANALYSIS3] Variable <variable name> is used as both a single and multifield variable in
the LHS.
Variables on the LHS of a rule cannot be bound to both single and multifield variables.

Example:
CLIPS> (defrule error (a ?x $?x) =>)

[ANALYSIS4] Variable <variable name> [found in the expression <expression>]
was referenced in CE <CE number> <field or slot identifier> before being defined
A variable cannot be referenced before it is defined and, thus, results in this error message.

Example:
CLIPS> (defrule error (a ~?x) =>)

[ARGACCES1] Function <name> expected exactly <number> argument(s).
This error occurs when a function that expects a precise number of argument(s) receives an
incorrect number of arguments.

[ARGACCES1] Function <name> expected at least <number> argument(s).
This error occurs when a function does not receive the minimum number of argument(s) that it
expected.

```
352 Appendix F: CLIPS Error Messages
```

[ARGACCES1] Function <name> expected no more than <number> argument(s).
This error occurs when a function receives more than the maximum number of argument(s)
expected.

[ARGACCES2] Function <name> expected argument #<number> to be of type
<data-type>.
This error occurs when a function is passed the wrong type of argument.

[ARGACCES 3 ] Function <function-name> was unable to open file <file-name>.
This error occurs when the specified function cannot open a file.

[BLOAD1] Cannot load <construct type> construct with binary load in effect.
If the bload command was used to load in a binary image, then the named construct cannot be
entered until a clear command has been performed to remove the binary image.

[BLOAD2] File <file-name> is not a binary construct file.
This error occurs when the bload command is used to load a file that was not created with the
bsave command.

[BLOAD3] File <file-name> is an incompatible binary construct file.
This error occurs when the bload command is used to load a file that was created with the bsave
command using a different version of CLIPS.

[BLOAD4] The CLIPS environment could not be cleared.
Binary load cannot continue.
A binary load cannot be performed unless the current CLIPS environment can be cleared.

[BLOAD5] Some constructs are still in use by the current binary image:
<construct-name 1>
<construct-name 2>
...
<construct-name N>
Binary <operation> cannot continue.
This error occurs when the current binary image cannot be cleared because some constructs are
still being used. The <operation> in progress may either be a binary load or a binary clear.

[BLOAD6] The following undefined functions are referenced by this binary image:
<function-name 1>
<function-name 2>
...
<function-name N>
This error occurs when a binary image is loaded that calls functions which were available in the
CLIPS executable that originally created the binary image, but which are not available in the
CLIPS executable that is loading the binary image.

```
CLIPS Basic Programming Guide 353
```

[BSAVE1] Cannot perform a binary save while a binary load is in effect.
The bsave command does not work when a binary image is loaded.

[CLASSEXM1] Inherited slot <slot-name> from class <class-name> is not valid for
function <name>.
This error message occurs when functions expecting a slot name defined for a class is given an
inherited slot.

Example:
CLIPS>
(defclass ORDER (is-a USER)
(slot id (visibility private)))
CLIPS> (defclass SPECIAL-ORDER (is-a ORDER))
CLIPS> (slot-publicp SPECIAL-ORDER id)

[CLASSFUN1] Unable to find class <class name> in function <function name>.
This error message occurs when a function is given a non-existent class name.

Example:
CLIPS> (class-slots MACHINE)

[CLASSFUN2] Maximum number of simultaneous class hierarchy traversals exceeded
<number>.
This error is usually caused by too many simultaneously active instance-set queries, e.g.,
do-for-all-instances. The direct or indirect nesting of instance-set query functions is limited in the
following way:

Ci is the number of members in an instance-set for the ith nested instance-set query function.

N is the number of nested instance-set query functions.

```
<= 256 (the default upper limit)
```

Example:
CLIPS>
(deffunction my-func ()
(do-for-instance ((?a USER) (?b USER) (?c USER)) TRUE
(println ?a " " ?b " " ?c)))
; The sum here is C 1 = 3 which is OK.
CLIPS>
(do-for-all-instances ((?a OBJECT) (?b OBJECT)) TRUE
(my-func))

```
; The sum here is C 1 + C 2 = 2 + 3 = 5 which is OK.
```

```
354 Appendix F: CLIPS Error Messages
```

The default upper limit of 256 should be sufficient for most if not all applications. However, the
limit may be increased by editing the header file object.h and recompiling CLIPS.

[CLASSPSR1] An abstract class cannot be reactive.
Only concrete classes can be reactive.

Example:
CLIPS>
(defclass MACHINE (is-a USER)
(role abstract)
(pattern-match reactive))

[CLASSPSR2] Cannot redefine a predefined system class.
Predefined system classes cannot be modified by the user.

Example:
CLIPS> (defclass STRING (is-a NUMBER))

[CLASSPSR3] Class <name> cannot be redefined while outstanding references to it still
exist.
This error occurs when an attempt to redefine a class is made under one or both of the following
two circumstances:

```
1) The class (or any of its subclasses) has instances.
```

```
2) The class (or any of its subclasses) appear in the parameter restrictions of any generic function
method.
```

Before the class can be redefined, all such instances and methods must be deleted.

Example:
CLIPS> (defclass A (is-a USER))
CLIPS> (defmethod AM ((?a A LEXEME)))
CLIPS> (defclass A (is-a OBJECT)))

[CLASSPSR4] The <attribute> class attribute is already declared.
Only one specification of a class attribute is allowed.

Example:
CLIPS>
(defclass A (is-a USER)
(role abstract)
(role concrete))

[CLSLTPSR1] The <slot-name> slot for class <class-name> is already specified.
Slots in a defclass must be unique.

```
CLIPS Basic Programming Guide 355
```

Example:
CLIPS>
(defclass ORDER (is-a USER)
(slot id)
(slot id))

[CLSLTPSR2] The <name> facet for slot <slot-name> is already specified.
Only one occurrence of a facet per slot is allowed.

Example:
CLIPS>
(defclass ORDER (is-a USER)
(slot id (access read-only)
(access read-write)))

[CLSLTPSR3] The 'cardinality' facet can only be used with multifield slots.
Single-field slots by definition have a cardinality of one.

Example:
CLIPS>
(defclass PERSON (is-a USER)
(slot favorites (cardinality 0 5)))

[CLSLTPSR4] Slots with an 'access' facet value of 'read-only' must have a default value.
Since slots cannot be unbound and read-only slots cannot be set after initial creation of the
instance, read-only slots must have a default value.

Example:
CLIPS>
(defclass PERSON (is-a USER)
(slot age (access read-only)
(default ?NONE)))

[CLSLTPSR5] Slots with an 'access' facet value of 'read-only' cannot have a write accessor.
Since read-only slots cannot be changed after initializationof the instance, a write accessor
(put- message-handler) is not allowed.

Example:
CLIPS>
(defclass PERSON (is-a USER)
(slot age (access read-only)
(create-accessor write)))

```
356 Appendix F: CLIPS Error Messages
```

[CLSLTPSR6] Slots with a 'propagation' value of 'no-inherit' cannot have a 'visibility'
facet value of 'public'.
no-inherit slots are by definition not accessible to subclasses and thus only visible to the parent
class.

Example:
CLIPS>
(defclass PERSON (is-a USER)
(slot age (propagation no-inherit)
(visibility public)))

[COMMLINE1] Expected a '(', constant, or global variable.
This message occurs when a top-level command does not begin with a '(', constant, or global
variable.

Example:
CLIPS> )

[COMMLINE2] Expected a command.
This message occurs when a top-level command is not a symbol.

Example:
CLIPS> ("facts")

[CONSCOMP1] Invalid file name <fileName> contains '.'
A '.' cannot be used in the file name prefix that is passed to the constructs-to-c command since this
prefix is used to generate file names and some operating systems do not allow more than one '.' to
appear in a file name.

[CONSCOMP2] Aborting because the base file name may cause the fopen maximum of
<integer> to be violated when file names are generated.
The constructs-to-c command generates file names using the file name prefix supplied as an
argument. If this base file name is longer than the maximum supported by the operating system,
then the possibility exists that files may be overwritten.

[CONSTRCT1] Some constructs are still in use. Clear cannot continue.
This error occurs when the clear command is issued when a construct is in use (such as a rule that
is firing).

[CSTRCPSR1] Expected the beginning of a construct.
This error occurs when the load command expects a left parenthesis followed a construct type and
these token types are not found.

[CSTRCPSR2] Missing name for <construct-type> construct.
This error occurs when the name is missing for a construct that requires a name.

```
CLIPS Basic Programming Guide 357
```

Example:
CLIPS> (defgeneric ())

[CSTRCPSR3] Cannot define <construct-type> <construct-name> because of an
import/export conflict.
or
[CSTRCPSR3] Cannot define defmodule <defmodule-name> because of an import/export
conflict cause by the <construct-type> <construct-name>.
A construct cannot be defined if defining the construct would allow two different definitions of
the same construct type and name to both be visible to any module.

Example:
CLIPS> (defmodule MAIN (export ?ALL))
CLIPS> (deftemplate MAIN::start)
CLIPS> (defmodule DATA (import MAIN ?ALL))
CLIPS> (deftemplate DATA::start (slot file-name))

[CSTRCPSR4] Cannot redefine <construct-type> <construct-name> while it is in use.
A construct cannot be redefined while it is being used by another construct or other data structure
(such as a fact or instance).

Example:
CLIPS> (deftemplate person)
CLIPS> (assert (person))
<Fact-1>
CLIPS> (deftemplate person (slot age))

[CSTRNCHK1] Message Varies
This error ID covers a range of messages indicating a type, value, range, or cardinality violation.

Example:
CLIPS> (deftemplate person (slot age (type INTEGER)))
CLIPS> (assert (person (age thirteen)))

[CSTRNPSR1] The <first attribute name> attribute conflicts with the <second attribute
name> attribute.
This error message occurs when two slot attributes conflict.

Example:
CLIPS> (deftemplate person (slot age (type SYMBOL) (range 0 120)))

[CSTRNPSR2] Minimum <attribute> value must be less than or equal to the maximum
<attribute> value.
The minimum attribute value for the range and cardinality attributes must be less than or equal to
the maximum attribute value for the attribute.

```
358 Appendix F: CLIPS Error Messages
```

Example:
CLIPS> (deftemplate person (slot age (range 120 0)))

[CSTRNPSR3] The <first attribute name> attribute cannot be used in conjunction with
the <second attribute name> attribute.
The use of some slot attributes excludes the use of other slot attributes.

Example:
CLIPS>
(deftemplate person
(slot gender (allowed-values male)
(allowed-symbols female)))

[CSTRNPSR4] Value does not match the expected type for the <attribute name> attribute.
The arguments to an attribute must match the type expected for that attribute (e.g. integers must
be used for the allowed-integers attribute).

Example:
CLIPS>
(deftemplate person
(slot gender (allowed-strings male female)))

[CSTRNPSR5] The 'cardinality' attribute can only be used with multifield slots.
The cardinality attribute can only be used for slots defined with the multislot keyword.

Example:
CLIPS> (deftemplate person (slot age (cardinality 1 1)))

[CSTRNPSR6] Minimum 'cardinality' value must be greater than or equal to zero.
A multislot with no value has a cardinality of 0. It is not possible to have a lower cardinality.

Example:
CLIPS> (deftemplate person (multislot hobbies (cardinality -1 5)))

[DEFAULT1] The default value for a single field slot must be a single field value.
This error occurs when the default or default-dynamic attribute for a single-field slot does not
contain a single value or an expression returning a single value.

Example:
CLIPS> (deftemplate person (slot age (default)))

[DFFNXPSR1] Deffunctions are not allowed to replace constructs.
A deffunction cannot have the same name as any construct.

```
CLIPS Basic Programming Guide 359
```

Example:
CLIPS> (deffunction defgeneric ())

[DFFNXPSR2] Deffunctions are not allowed to replace external functions.
A deffunction cannot have the same name as any system or user-defined external function.

Example:
CLIPS> (deffunction + ())

[DFFNXPSR3] Deffunctions are not allowed to replace generic functions.
A deffunction cannot have the same name as any generic function.

Example:
CLIPS> (defgeneric start)
CLIPS> (deffunction start ())

[DFFNXPSR4] Deffunction <name> may not be redefined while it is executing.
A deffunction can be loaded at any time except when a deffunction of the same name is already
executing.

Example:
CLIPS>
(deffunction create ()
(build "(deffunction create ())"))
CLIPS> (create)

[DFFNXPSR5] Defgeneric <name> imported from module <module name> conflicts with
this deffunction.
A deffunction cannot have the same name as any generic function imported from another module.

Example:
CLIPS> (defmodule MAIN (export ?ALL))
CLIPS> (defmethod start ())
CLIPS> (defmodule DATA (import MAIN ?ALL))
CLIPS> (deffunction start)

[DRIVE1] This error occurred in the join network.
Problem resides in associated join
Of pattern #<pattern-number> in rule <rule-name>
This error pinpoints other evaluation errors associated with evaluating an expression within the
join network. The specific pattern of the problem rules is identified.

[EMATHFUN1] Domain error for <function-name> function.
This error occurs when an argument passed to a math function is not in the domain of values for
which a return value exists.

```
360 Appendix F: CLIPS Error Messages
```

[EMATHFUN2] Argument overflow for <function-name> function.
This error occurs when an argument to an extended math function would cause a numeric overflow.

[EMATHFUN3] Singularity at asymptote in <function-name> function.
This error occurs when an argument to a trigonometric math function would cause a singularity.

[EVALUATN1] Variable <name> is unbound
This error occurs when a local variable not set by a previous call to bind is accessed at the top-
level.

Example:
CLIPS> (progn ?error)

[EXPRNPSR1] A function name must be a symbol.
In the following example, '~' is recognized by CLIPS as an operator, not a function:

Example:
CLIPS> (+ (~ 3 4) 4)

[EXPRNPSR2] Expected a constant, variable, or expression.
In the following example, '~' is an operator and is illegal as an argument to a function call:

Example:
CLIPS> (<= ~ 4)

[EXPRNPSR3] Missing function declaration for <name>.
CLIPS does not recognize <name> as a declared function and gives this error message.

Example:
CLIPS> (undefined)

[EXPRNPSR4] $ Sequence operator not a valid argument for <name>.
The sequence expansion operator cannot be used with certain functions.

Example:
CLIPS> (set-sequence-operator-recognition TRUE)
FALSE
CLIPS> (defrule error (list $?v) => (assert (copy-list $?v)))

[FACTMCH1] This error occurred in the fact pattern network
Currently active fact: <newly assert fact>
Problem resides in slot <slot name>
Of pattern #<pattern-number> in rule <rule name>
This error pinpoints other evaluation errors associated with evaluating an expression within the
pattern network. The specific pattern and field of the problem rules are identified.

```
CLIPS Basic Programming Guide 361
```

[FACTMNGR1] Facts may not be retracted during pattern-matching
or
[FACTMNGR2] Facts may not be asserted during pattern-matching
Functions used on the LHS of a rule should not have side effects (such as the creation of a new
instance or fact).

Example:
CLIPS> (defrule error (start) (test (assert (end))) =>)
CLIPS> (assert (start))

[FACTRHS1] Implied deftemplate <name> cannot be created with binary load in effect.
This error occurs when an assert is attempted for a deftemplate which does not exist in a runtime
or active bload image. In other situations, CLIPS will create an implied deftemplate if one does
not already exist.

Example:
CLIPS> (clear)
CLIPS> (bsave error.bin)
TRUE
CLIPS> (bload error.bin)
TRUE
CLIPS> (assert (error))

[GENRCCOM1] No such generic function <name> in function undefmethod.
This error occurs when the generic function name passed to the undefmethod function does not
exist.

Example:
CLIPS> (undefmethod process 3)

[GENRCCOM2] Expected a valid method index in function undefmethod.
This error occurs when an invalid method index is passed to undefmethod (e.g. a negative integer
or a symbol other than \*).

Example:
CLIPS> (defmethod process ())
CLIPS> (undefmethod process a)

[GENRCCOM3] Incomplete method specification for deletion.
It is illegal to specify a non-wildcard method index when a wildcard is given for the generic
function in the undefmethod command.

Example:
CLIPS> (undefmethod \* 1)

```
362 Appendix F: CLIPS Error Messages
```

[GENRCCOM4] Cannot remove implicit system function method for generic function
<name>.
A method corresponding to a system defined function cannot be deleted.

Example:
CLIPS> (defmethod integer ((?x SYMBOL)) 0)
CLIPS> (list-defmethods integer)
integer #SYS1 (NUMBER)
integer #2 (SYMBOL)
For a total of 2 methods.
CLIPS> (undefmethod integer 1)

[GENRCEXE1] No applicable methods for <name>.
The generic function call arguments do not satisfy any method’s parameter restrictions.

Example:
CLIPS> (defmethod process ())
CLIPS> (process 1 2)

[GENRCEXE2] Shadowed methods not applicable in current context.
No shadowed method is available when the call-next-method function is called.

Example:
CLIPS> (call-next-method)

[GENRCEXE3] Unable to determine class of <value> in generic function <name>.
The class or type of a generic function argument could not be determined for comparison to a
method type restriction.

Example:
CLIPS> (defmethod process ((?a INTEGER)))
CLIPS> (process [invalid])

[GENRCEXE4] Generic function <name> method #<index> is not applicable to the given
arguments.
This error occurs when call-specific-method is called with an inappropriate set of arguments for
the specified method.

Example:
CLIPS> (defmethod process ())
CLIPS> (call-specific-method process 1 a)

[GENRCFUN1] Defgeneric <name> cannot be modified while one of its methods is
executing.
Defgenerics can’t be redefined while one of their methods is currently executing.

Example:

```
CLIPS Basic Programming Guide 363
```

```
CLIPS> (defgeneric process)
CLIPS> (defmethod process () (build "(defgeneric process)"))
CLIPS> (process)
```

[GENRCFUN2] Unable to find method <name> #<index> in function <name>.
No generic function method of the specified index could be found by the named function.

Example:
CLIPS> (defmethod process 1 ())
CLIPS> (ppdefmethod process 2)

[GENRCFUN3] Unable to find generic function <name> in function <name>.
No generic function method of the specified index could be found by the named function.

Example:
CLIPS> (preview-generic error)

[GENRCPSR1] Expected ')' to complete defgeneric.
A right parenthesis completes the definition of a generic function header.

Example:
CLIPS> (defgeneric process ())

[GENRCPSR2] New method #<index1> would be indistinguishable from method #<index2>.
An explicit index has been specified for a new method that does not match that of an older method
which has identical parameter restrictions.

Example:
CLIPS> (defmethod process 1 ((?a INTEGER)))
CLIPS> (defmethod process 2 ((?a INTEGER)))

[GENRCPSR3] Defgenerics are not allowed to replace constructs.
A generic function cannot have the same name as any construct.

[GENRCPSR4] Deffunction <name> imported from module <module name> conflicts with
this defgeneric.
A deffunction cannot have the same name as any generic function imported from another module.

Example:
CLIPS> (defmodule MAIN (export ?ALL))
CLIPS> (deffunction process ())
CLIPS> (defmodule DATA (import MAIN ?ALL))
CLIPS> (defmethod process)

```
364 Appendix F: CLIPS Error Messages
```

[GENRCPSR5] Defgenerics are not allowed to replace deffunctions.
A generic function cannot have the same name as any deffunction.

[GENRCPSR6] Method index out of range.
A method index cannot be greater than the maximum value of an integer or less than 1.

Example:
CLIPS> (defmethod process 0)

[GENRCPSR7] Expected a '(' to begin method parameter restrictions.
A left parenthesis must begin a parameter restriction list for a method.

Example:
CLIPS> (defmethod process)

[GENRCPSR8] Expected a variable for parameter specification.
A method parameter with restrictions must be a variable.

Example:
CLIPS> (defmethod process ((value)))

[GENRCPSR9] Expected a variable or '(' for parameter specification.
A method parameter must be a variable with or without restrictions.

Example:
CLIPS> (defmethod process (value))

[GENRCPSR10] Query must be last in parameter restriction.
A query parameter restriction must follow a type parameter restriction (if any).

Example:
CLIPS> (defmethod process ((?a (< ?a 1) INTEGER)))

[GENRCPSR11] Duplicate classes/types not allowed in parameter restriction.
A method type parameter restriction may have only a single occurrence of a particular class.

Example:
CLIPS> (defmethod process ((?a INTEGER INTEGER)))

[GENRCPSR12] Binds are not allowed in query expressions.
Binding new variables in a method query parameter restriction is illegal.

Example:
CLIPS> (defmethod process ((?a (bind ?b 1))))

```
CLIPS Basic Programming Guide 365
```

[GENRCPSR13] Expected a valid class/type name or query.
Method parameter restrictions consist of zero or more class names and an optional query
expression.

Example:
CLIPS> (defmethod process ((?a 34)))

[GENRCPSR14] Unknown class/type in method.
Classes in method type parameter restrictions must already be defined.

Example:
CLIPS> (defmethod process ((?a UNKNOWN-CLASS)))

[GENRCPSR15] Class <name> is redundant.
All classes in a method type parameter restriction should be unrelated.

Example:
CLIPS> (defmethod process ((?a INTEGER NUMBER)))

[GENRCPSR16] The system function <name> cannot be overloaded.
Some system functions canot be overloaded.

Example:
CLIPS> (defmethod if ())

[GENRCPSR17] Cannot replace the implicit system method #<integer>.
A system function can not be overloaded with a method that has the exact number and types of
arguments.

Example:
CLIPS> (defmethod integer ((?x NUMBER)) (\* 2 ?x))

[GLOBLDEF1] Global variable <variable name> is unbound.
A global variable must be defined before it can be accessed at the command prompt or elsewhere.

Example:
CLIPS> (clear)
CLIPS> ?_x_

[GLOBLPSR1] Global variable <variable name> was referenced, but is not defined.
A global variable must be defined before it can be accessed at the command prompt or elsewhere.

Example:
CLIPS> (clear)
CLIPS> (bind ?_x_ 1)

```
366 Appendix F: CLIPS Error Messages
```

[INHERPSR1] A class may not have itself as a superclass.
A class may not inherit from itself.

Example:
CLIPS> (defclass MACHINE (is-a MACHINE))

[INHERPSR2] A class may inherit from a superclass only once.
All direct superclasses of a class must be unique.

Example:
CLIPS> (defclass MACHINE (is-a USER USER))

[INHERPSR3] A class must be defined after all its superclasses.
Subclasses must be defined last.

Example:
CLIPS> (defclass MACHINE (is-a DEVICE))

[INHERPSR4] A class must have at least one superclass.
All user-defined classes must have at least one direct superclass.

Example:
CLIPS> (defclass MACHINE (is-a))

**[INHERPSR5] Partial precedence list formed: <classa> <classb> ... <classc>
Precedence loop in superclasses: <class1> <class2> ... <classn>** <class1>
No class precedence list satisfies the rules specified in section 9.3.1.1 for the given direct
superclass list. The message shows a conflict for <class1> because the precedence implies that
<class1> must both precede and succeed <class2> through <classn>. The full loop can be used to
help identify which particular classes are causing the problem. This loop is not necessarily the only
loop in the precedence list; it is the first one detected. The part of the precedence list which was
successfully formed is also listed.

Example:
CLIPS> (defclass A (is-a MULTIFIELD FLOAT SYMBOL))
CLIPS> (defclass B (is-a SYMBOL FLOAT))
CLIPS> (defclass C (is-a A B))

[INHERPSR6] A user-defined class cannot be a subclass of <name>.
The INSTANCE, INSTANCE-NAME, and INSTANCE-ADDRESS classes cannot have any
subclasses.

Example:
CLIPS> (defclass MACHINE (is-a INSTANCE))

```
CLIPS Basic Programming Guide 367
```

[INSCOM1] Undefined type in function <name>.
The evaluation of an expression yielded something other than a recognized class or primitive type.

[INSFILE1] Function <function-name> could not completely process file <name>.
This error occurs when an instance definition is improperly formed in the input file for the
load-instances, restore-instances, or bload-instances command.

Example:
CLIPS> (load-instances bogus.txt)

[INSFILE2] File <file-name> is not a binary instances file.
or
[INSFILE3] File <file-name> is not a compatible binary instances file.
This error occurs when bload-instances attempts to load a file that was not created with
bsave-instances or when the file being loaded was created by a different version of CLIPS.

Example:
CLIPS> (reset)
CLIPS> (save-instances data.ins)
1
CLIPS> (bload-instances data.ins)

[INSFILE4] Function 'bload-instances' is unable to load instance <instance-name>.
This error occurs when an instance specification in the input file for the bload-instances command
could not be created.

Example:
CLIPS> (defclass A (is-a USER))
CLIPS> (make-instance of A)
[gen1]
CLIPS> (bsave-instances data.bin)
1
CLIPS> (clear)
CLIPS> (defclass A (is-a USER) (role abstract))
CLIPS> (bload-instances data.bin)

[INSFUN1] Expected a valid instance in function <name>.
The named function expected an instance-name or address as an argument.

Example:
CLIPS> (initialize-instance 34)

[INSFUN2] No such instance <name> in function <name>.
This error occurs when the named function cannot find the specified instance.

Example:
CLIPS> (instance-address [invalid-instance])

```
368 Appendix F: CLIPS Error Messages
```

[INSFUN3] No such slot <name> in function <name>.
This error occurs when the named function cannot find the specified slot in an instance or class.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (slot-writablep MACHINE id)

[INSFUN4] Invalid instance-address in function <name>, argument #<integer>.
This error occurs when an attempt is made to use the address of a deleted instance.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (defglobal ?_selected-machine_ = (instance-address [m]))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (class ?_selected-machine_)

[INSFUN5] Cannot modify reactive instance slots while pattern-matching is in process.
CLIPS does not allow reactive instance slots to be changed while pattern-matching is taking place.
Functions used on the LHS of a rule should not have side effects (such as the changing slot values).

Example:
CLIPS>
(defclass MACHINE (is-a USER)
(slot id))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS>
(defrule error
(start)
(test (send [m] put-id 34))
=>)
CLIPS> (assert (start))

[INSFUN6] Unable to pattern-match on shared slot <name> in class <name>.
This error occurs when the number of simultaneous class hierarchy traversals is exceeded while
pattern-matching on a shared slot. See the related error message [CLASSFUN2] for more details.

[INSFUN7] The value<multifield-value> is illegal for single-field slot <name> of instance
<name> found in <function-call or message-handler>.
Single-field slots in an instance can hold only one atomic value.

Example:
CLIPS>
(defclass MACHINE (is-a USER)
(slot id))

```
CLIPS Basic Programming Guide 369
```

```
CLIPS>
(deffunction assign-id (?ins ?id)
(send ?ins put-id ?id))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (assign-id [m] (create$ 1 2 3 4))
```

[INSFUN8] Void function illegal value for slot <name> of instance <name> found in
<function-call or message-handler>.
Only functions which have a return value can be used to generate values for an instance slot.

Example:
CLIPS>
(defclass MACHINE (is-a USER)
(slot id))
CLIPS>
(defmessage-handler MACHINE error ()
(bind ?self:id (agenda)))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (send [m] error)

[INSMNGR1] Expected a valid name for new instance.
make-instance expects a symbol or an instance-name for the name of a new instance.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (make-instance 34 of MACHINE)

[INSMNGR2] Expected a valid class name for new instance.
make-instance expects a symbol for the class of a new instance.

Example:
CLIPS> (make-instance m of 34)

[INSMNGR3] Cannot create instances of abstract class <name>.
Direct instances of abstract classes, such as the predefined system classes, are illegal.

Example:
CLIPS> (make-instance [m] of USER)

[INSMGNR4] The instance <name> has a slot-value which depends on the instance
definition.
The initialization of an instance is recursive in that a slot-override or default-value tries to create
or reinitialize the same instance.

Example:
CLIPS>

```
370 Appendix F: CLIPS Error Messages
```

```
(defclass MACHINE (is-a USER)
(slot id))
CLIPS> (make-instance m of MACHINE (id (make-instance m of MACHINE)))
```

[INSMNGR5] Unable to delete old instance <name>.
make-instance will attempt to delete an old instance of the same name if it exists. This error occurs
if that deletion fails.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS>
(defmessage-handler MACHINE delete around ()
(if (neq (instance-name ?self) [m]) then
(call-next-handler)))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (make-instance m of MACHINE)

[INSMNGR6] Cannot delete instance <name> during initialization.
The evaluation of a slot-override in make-instance or initialize-instance attempted to delete the
instance.

Example:
CLIPS>
(defclass MACHINE (is-a USER)
(slot id))
CLIPS>
(defmessage-handler MACHINE put-id after ($?any)
(delete-instance))
CLIPS> (make-instance m of MACHINE (id 3))

[INSMNGR7] Instance <name> is already being initialized.
An instance cannot be reinitialized during initialization.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS>
(defmessage-handler MACHINE init after ()
(initialize-instance ?self))
CLIPS> (initialize-instance m)

[INSMNGR8] An error occurred during the initialization of instance <name>.
This message is displayed when an evaluation error occurs while the init message is executing for
an instance.

[INSMNGR9] Expected a valid slot name for slot-override.
make-instance and initialize-instance expect symbols for slot names.

```
CLIPS Basic Programming Guide 371
```

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (make-instance m of MACHINE (34 3))

[INSMNGR10] Cannot create instances of reactive classes while pattern-matching is in
process.
CLIPS does not allow instances of reactive classes to be created while pattern-matching is taking
place. Functions used on the LHS of a rule should not have side effects (such as the creation of a
new instance or fact).

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS>
(defrule error
(start)
(test (make-instance of MACHINE))
=>)
CLIPS> (assert (start))

[INSMNGR11] Invalid module specifier in new instance name.
This error occurs when the module specifier in the instance-name is illegal (such as an undefined
module name).

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (make-instance INVALID::m of MACHINE)

[INSMNGR12] Cannot delete instances of reactive classes while pattern-matching is in
process.
CLIPS does not allow instances of reactive classes to be deleted while pattern-matching is taking
place. Functions used on the LHS of a rule should not have side effects (such as the deletion of a
new instance or the retraction of a fact).

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS>
(defrule error
(start)
(test (send [m] delete))
=>)
CLIPS> (assert (start))

```
372 Appendix F: CLIPS Error Messages
```

[INSMNGR13] Slot <slot-name> does not exist in instance <instance-name>.
This error occurs when the slot name of a slot override does not correspond to any of the valid slot
names for an instance.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (make-instance of MACHINE (id 33))

[INSMNGR14] Override required for slot <slot-name> in instance <instance-name>.
If the ?NONE keyword was specified with the default attribute for a slot, then a slot override must
be provided when an instance containing that slot is created.

Example:
CLIPS>
(defclass MACHINE (is-a USER)
(slot id (default ?NONE)))
CLIPS> (make-instance of MACHINE)

[INSMNGR15] init-slots not valid in this context.
The special function init-slots (for initializing slots of an instance to the class default values) can
only be called during the dispatch of an init message for an instance, i.e., in an init
message-handler.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS>
(defmessage-handler MACHINE error ()
(init-slots))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (send [m] error)

[INSMNGR16] The instance name <instance-name> is in use by an instance of class <class-
name>.
An instance of one class cannot be created using an instance name belonging to a different class.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (defclass PRODUCT (is-a USER))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (make-instance m of PRODUCT)

[INSMODDP1] Direct/message-modify message valid only in modify-instance.
The direct-modify and message-modify message-handlers attached to the class USER can only
be called as a result of the appropriate message being sent.by the modify-instance or

```
CLIPS Basic Programming Guide 373
```

message-modify-instance functions. Additional handlers may be defined, but the message can
only be sent in this context.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (send [m] direct-modify 0)

[INSMODDP2] Direct/message-duplicate message valid only in duplicate-instance.
The direct-duplicate and message-duplicate message-handlers attached to the class USER can
only be called as a result of the appropriate message being sent.by the duplicate-instance or
message-duplicate-instance functions. Additional handlers may be defined, but the message can
only be sent in this context.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (send [m] direct-duplicate 0 0)

[INSMODDP3] Instance copy must have a different name in duplicate-instance.
If an instance-name is specified for the new instance in the call to duplicate-instance, it must be
different from the source instance’s name.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (duplicate-instance m to m)

[INSMULT1] Function <name> cannot be used on single-field slot <name> in instance
<name>.
Some functions, such as slot-insert$, can only operate on multifield slots.

Example:
CLIPS>
(defclass MACHINE (is-a USER)
(slot id))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (slot-insert$ m id 273 383 377)

[INSQYPSR1] Duplicate instance-set member variable name in function <name>.
Instance-set member variables in an instance-set query function must be unique.

Example:

```
374 Appendix F: CLIPS Error Messages
```

```
CLIPS> (any-instancep ((?a OBJECT) (?a OBJECT)) TRUE)
```

[INSQYPSR2] Binds are not allowed in instance-set query in function <name>.
An instance-set query cannot bind variables.

Example:
CLIPS>
(any-instancep ((?a OBJECT) (?b OBJECT))
(bind ?c 1))

[INSQYPSR3] Cannot rebind instance-set member variable <name> in function <name>.
Instance-set member variables cannot be changed within the actions of an instance-set query
function.

Example:
CLIPS>
(do-for-all-instances ((?a USER))
(if (slot-existp ?a age) then
(> ?a:age 30))
(bind ?a (send ?a get-brother)))

[IOFUN1] Illegal logical name used for <function name> function.
A logical name must be either a symbol, string, instance-name, float, or integer.

Example:
(printout invalid "Hello World!" crlf)

[IOFUN2] Logical name <logical name> already in use.
A logical name cannot be associated with two different files.

Example:
CLIPS> (open "out.txt" output "w")
TRUE
CLIPS> (open "out2.txt" output "w")

[MEMORY1] Out of memory
This error indicates insufficient memory exists to expand internal structures enough to allow
continued operation (causing an exit to the operating system).

[MISCFUN1] The function 'expand$' must be used in the argument list of a function call.
or
[MISCFUN1] Sequence expansion must be used in the argument list of a function call.
Sequence expansion and the expand$ function may not be used unless it is within the argument
list of another function.

Example:
CLIPS> (expand$ (create$ red green blue))

```
CLIPS Basic Programming Guide 375
```

[MODULDEF1] Illegal use of the module specifier.
The module specifier can only be used as part of a defined construct’s name or as an argument to
a function.

Example:
CLIPS> (deftemplate person (slot name) (slot age))
CLIPS> (defrule match (MAIN::person) =>)

[MODULPSR1] Module <module name> does not export any constructs.
or
[MODULPSR1] Module <module name> does not export any <construct type> constructs.
or
[MODULPSR1] Module <module name> does not export the <construct type> <construct
name>.
A construct cannot be imported from a module unless the defmodule exports that construct.

Example:
CLIPS> (clear)
CLIPS> (defmodule START)
CLIPS> (deftemplate START::data)
CLIPS> (defmodule FINISH (import START deftemplate data))

[MSGCOM1] Incomplete message-handler specification for deletion.
It is illegal to specify a non-wildcard handler index when a wildcard is given for the class in the
external C function UndefmessageHandler(). This error can only be generated when a
user-defined external function linked with CLIPS calls this command incorrectly.

[MSGCOM2] Unable to find message-handler <name> <type> for class <name> in
function <name>.
This error occurs when the named function cannot find the specified message-handler.

Example:
CLIPS> (ppdefmessage-handler USER print around)

[MSGCOM3] Unable to delete message-handlers.
This error occurs when a message-handler can’t be deleted (such as when a binary image is
loaded).

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (defmessage-handler MACHINE start ())
CLIPS> (bsave "program.bin")
TRUE
CLIPS> (bload "program.bin")
TRUE

```
376 Appendix F: CLIPS Error Messages
```

```
CLIPS> (undefmessage-handler MACHINE start)
```

[MSGFUN1] No applicable primary message-handlers found for <message>.
No primary message-handler attached to the object’s classes matched the name of the message.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (send [m] invalid-message)

[MSGFUN2] Message-handler <name> <type> in class <name> expected exactly/at least
<number> argument(s).
The number of message arguments was inappropriate for one of the applicable message-handlers.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (defmessage-handler MACHINE start (?start ?duration))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (send [m] start)

[MSGFUN3] Write access denied for slot <name> in instance <name>.
This error occurs when an attempt is made to change the value of a read-only slot.

Example:
CLIPS>
(defclass MACHINE (is-a USER)
(slot id (access initialize-only)))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (send [m] put-id)

[MSGFUN4] The function <function> may only be called from within message-handlers.
The named function operates on the active instance of a message and thus can only be called by
message-handlers.

Example:
CLIPS> (ppinstance)

[MSGFUN5] The function <function> operates only on instances.
The named function operates on the active instance of a message and can only handle instances
of user-defined classes (not primitive type objects).

Example:
CLIPS>
(defmessage-handler INTEGER print ()
(ppinstance))

```
CLIPS Basic Programming Guide 377
```

```
CLIPS> (send 34 print)
```

[MSGFUN6] Private slot <slot-name> of class <class-name> cannot be accessed directly by
handlers attached to class <class-name>
A subclass which inherits private slots from a superclass may not access those slots using the ?self
variable. This error can also occur when a superclass tries to access via dynamic-put or
dynamic-get a private slot in a subclass.

Example:
CLIPS> (defclass DEVICE (is-a USER) (slot id))
CLIPS> (defclass MACHINE (is-a DEVICE))
CLIPS> (defmessage-handler MACHINE mid () ?self:id)

[MSGFUN7] Unrecognized message-handler type in defmessage-handler in function
<function>.
Allowed message-handler types include primary, before, after, and around.

Example:
CLIPS> (defmessage-handler USER print behind ())

[MSGFUN8] Unable to delete message-handler(s) from class <name>.
This error occurs when an attempt is made to delete a message-handler attached to a class for
which any of the message-handlers are executing.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS>
(defmessage-handler MACHINE error ()
(undefmessage-handler MACHINE error primary))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (send [m] error)

[MSGPASS1] Shadowed message-handlers not applicable in current context.
No shadowed message-handler is available when the function call-next-handler or
override-next-handler is called.

Example:
CLIPS> (call-next-handler)

[MSGPASS2] No such instance <name> in function <name>.
This error occurs when the named function cannot find the specified instance.

Example:
CLIPS> (instance-address [invalid-instance])

```
378 Appendix F: CLIPS Error Messages
```

[MSGPASS3] Static reference to slot <name> of class <name> does not apply to
<instance-name> of <class-name>.
This error occurs when a static reference to a slot in a superclass by a message-handler attached to
that superclass is incorrectly applied to an instance of a subclass which redefines that slot. Static
slot references always refer to the slot defined in the class to which the message-handler is
attached.

Example:
CLIPS>
(defclass DEVICE (is-a USER)
(slot id))
CLIPS>
(defclass MACHINE (is-a DEVICE)
(slot id))
CLIPS>
(defmessage-handler DEVICE access-id ()
?self:id)
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS> (send [m] access-id)

[MSGPSR1] A class must be defined before its message-handlers.
A message-handler can only be attached to an existing class.

Example:
CLIPS> (defmessage-handler UNDEFINED-CLASS process ())

[MSGPSR2] Cannot (re)define message-handlers during execution of other
message-handlers for the same class.
No message-handlers for a class can be loaded while any current message-handlers attached to the
class are executing.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (make-instance m of MACHINE)
[m]
CLIPS>
(defmessage-handler MACHINE build-new ()
(build "(defmessage-handler MACHINE new ())"))
CLIPS> (send [m] build-new)

[MSGPSR3] System message-handlers may not be modified.
There are four primary message-handlers attached to the class USER which cannot be modified:
init, delete, create and print.

Example:
CLIPS> (defmessage-handler USER init ())

```
CLIPS Basic Programming Guide 379
```

[MSGPSR4] Illegal slot reference in parameter list.
Direct slot references are allowed only within message-handler bodies.

Example:
CLIPS> (defmessage-handler USER process (?self:id))

[MSGPSR5] Active instance parameter cannot be changed.
?self is a reserved parameter for the active instance.

Example:
CLIPS>
(defmessage-handler USER process ()
(bind ?self 1))

[MSGPSR6] No such slot <name> in class <name> for ?self reference.
The symbol following the ?self: reference must be a valid slot for the class.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (defmessage-handler MACHINE id () ?self:id)

[MSGPSR7] Illegal value for ?self reference.
The symbol following the ?self: reference must be a symbol.

Example:
CLIPS> (defclass MACHINE (is-a USER))
CLIPS> (defmessage-handler MACHINE id () ?self:7)

[MSGPSR8] Message-handlers cannot be attached to the class <name>.
Message-handlers cannot be attached to the INSTANCE, INSTANCE-ADDRESS, or
INSTANCE-NAME classes.

Example:
CLIPS> (defmessage-handler INSTANCE process ())

[MULTIFUN1] Multifield index <index> out of range 1..<end range> in function <name>
or
[MULTIFUN1] Multifield index range <start>...<end> out of range 1..<end range> in
function <name>
This error occurs when a multifield manipulation function is passed a single index or range of
indices that does not fall within the specified range of allowed indices.

Example:
CLIPS> (delete$ (create$ red green blue) 4 4)

```
380 Appendix F: CLIPS Error Messages
```

[MULTIFUN2] Cannot rebind field variable in function <function>.
The field variable (if specified) cannot be rebound within the body of the progn$ or foreach
function.

Example:
CLIPS> (progn$ (?field (create$ a)) (bind ?field 3))

[OBJRTBLD1] No objects of existing classes can satisfy pattern.
No objects of existing classes could possibly satisfy the pattern. This error usually occurs when a
restriction placed on the is-a attribute is incompatible with slot restrictions before it in the pattern.

Example:
CLIPS> (defclass MACHINE (is-a USER) (slot id))
CLIPS> (defrule error (object (id ?) (is-a ~MACHINE)) =>)

[OBJRTBLD2] No objects of existing classes can satisfy <attribute-name> restriction in
object pattern.
The restrictions on <attribute> are such that no objects of existing classes (which also satisfy
preceding restrictions) could possibly satisfy the pattern.

Example:
CLIPS> (defrule error (object (invalid-slot ?)) =>)

[OBJRTBLD3] No objects of existing classes can satisfy pattern #<pattern-num>.
No objects of existing classes could possibly satisfy the pattern. This error occurs when the
constraints for a slot as given in the defclass(es) are incompatible with the constraints imposed by
the pattern.

Example:
CLIPS>
(defclass MACHINE (is-a USER)
(slot id (type INTEGER)))
CLIPS>
(defclass PRODUCT (is-a USER)
(slot id (type STRING))
(slot manufacturer))
CLIPS>
(defrule error
(object (id 100) (manufacturer ?))
=>)

[OBJRTBLD4] Multiple restrictions on attribute <attribute-name> not allowed.
Only one restriction per attribute is allowed per object pattern.

Example:
CLIPS> (defrule error (object (is-a ?) (is-a ?)) =>)

```
CLIPS Basic Programming Guide 381
```

[OBJRTBLD5] Undefined class <class-name> in object pattern.
Object patterns are applicable only to classes of objects which are already defined.

Example:
CLIPS> (defrule error (object (is-a UNDEFINED-CLASS)) =>)

[OBJRTMCH1] This error occurred in the object pattern network
Currently active instance: <instance-name>
Problem resides in slot <slot name> field #<field-index>
Of pattern #<pattern-number> in rule(s):
<problem-rules>+
This error pinpoints other evaluation errors associated with evaluating an expression within the
object pattern network. The specific pattern and field of the problem rules are identified.

[PATTERN1] The symbol <symbol name> has special meaning and may not be used as a
<use name>.
Certain keywords have special meaning to CLIPS and may not be used in situations that would
cause an ambiguity.

Example:
CLIPS> (deftemplate exists (slot id))

[PATTERN2] Single and multifield constraints cannot be mixed in a field constraint
Single and multifield variable constraints cannot be mixed in a field constraint (this restriction
does not include variables passed to functions with the predicate or return value constraints).

Example:
CLIPS> (defrule error (pattern ?x $?y ?x&~$?y) =>)

[PRCCODE1] Attempted to call a <construct> which does not exist.
In a CLIPS configuration without deffunctions and/or generic functions, an attempt was made to
call a deffunction or generic function from a binary image generated by the bsave command.

[PRCCODE2] Functions without a return value are illegal as <construct> arguments.
An evaluation error occurred while examining the arguments for a deffunction, generic function
or message.

Example:
CLIPS> (defmethod process (?a))
CLIPS> (process (instances))

```
382 Appendix F: CLIPS Error Messages
```

[PRCCODE3] Undefined variable <name> referenced in <where>.
Local variables in the actions of a deffunction, method, message-handler, or defrule must reference
parameters, variables bound within the actions with the bind function, or variables bound on the
LHS of a rule.

Example:
CLIPS> (defrule error => (+ ?a 3))

[PRCCODE4] Execution halted during the actions of <construct> <name>.
This error occurs when the actions of a rule, deffunction, generic function method or
message-handler are prematurely aborted due to an error.

[PRCCODE5] Variable <name> unbound [in <construct> <name>].
This error occurs when local variables in the actions of a deffunction, method, message-handler,
or defrule becomes unbound during execution as a result of calling the bind function with no
arguments.

Example:
CLIPS> (deffunction process () (bind ?a) ?a)
CLIPS> (process)

[PRCCODE6] This error occurred while evaluating arguments for the <construct>
<name>.
An evaluation error occurred while examining the arguments for a deffunction, generic function
method or message-handler.

Example:
CLIPS> (deffunction process (?a))
CLIPS> (process (+ (eval "(gensym)") 2))

[PRCCODE7] Duplicate parameter names not allowed.
Deffunction, method or message-handler parameter names must be unique.

Example:
CLIPS> (defmethod process ((?x INTEGER) (?x FLOAT)))

[PRCCODE8] No parameters allowed after wildcard parameter.
A wildcard parameter for a deffunction, method or message-handler must be the last parameter.

Example:
CLIPS> (defmethod process (($?x INTEGER) (?y SYMBOL)))

[PRCDRPSR1] Cannot rebind count variable in function loop-for-count.
The special variable ?count cannot be rebound within the body of the loop-for-count function.

Example:

```
CLIPS Basic Programming Guide 383
```

```
CLIPS> (loop-for-count (?count 10) (bind ?count 3))
```

[PRCDRPSR2] The return function is not valid in this context.
or
[PRCDRPSR2] The break function is not valid in this context.
The return and break functions can only be used within certain contexts (e.g. the break function
can only be used within a while loop and certain instance set query functions).

Example:
CLIPS> (return 3)

[PRCDRPSR3] Duplicate case found in switch function.
A case may be specified only once in a switch statement.

Example:
CLIPS> (switch a (case a then 8) (case a then 9))

[PRNTUTIL1] Unable to find <item> <item-name>
This error occurs when CLIPS cannot find the named item (check for typos).

[PRNTUTIL2] Syntax Error: Check appropriate syntax for <item>
This error occurs when the appropriate syntax is not used.

Example:
CLIPS> (if (> 3 4))

[PRNTUTIL3]
**_ CLIPS SYSTEM ERROR _**
ID = <error-id>
CLIPS data structures are in an inconsistent or corrupted state.
This error may have occurred from errors in user defined code.

---

This error indicates an internal problem within CLIPS (which may have been caused by user
defined functions or other user code). If the problem cannot be located within user defined code,
then the <error-id> should be reported.

[PRNTUTIL4] Unable to delete <item> <item-name>
This error occurs when CLIPS cannot delete the named item (e.g. a construct might be in use).
One example which will cause this error is an attempt to delete a deffunction or generic function
which is used in another construct (such as the RHS of a defrule or a default-dynamic facet of a
defclass slot).

[PRNTUTIL5] The <item> has already been parsed.
This error occurs when CLIPS has already parsed an attribute or declaration.

```
384 Appendix F: CLIPS Error Messages
```

[PRNTUTIL6] Local variables cannot be accessed by <function or construct>.
This error occurs when a local variable is used by a function or construct that cannot use global
variables.

Example:
CLIPS> (deffacts info (id ?x))

[PRNTUTIL7] Attempt to divide by zero in <function-name> function.
This error occurs when a function attempts to divide by zero.

Example:
CLIPS> (/ 3 0)

[PRNTUTIL8] This error occurred while evaluating the salience [for rule <name>]
When an error results from evaluating a salience value for a rule, this error message is given.

[PRNTUTIL9] Salience value out of range <min> to <max>
The range of allowed salience has an explicit limit; this error message will result if the value is out
of that range.

Example:
CLIPS> (defrule error (declare (salience 20000)) =>)

[PRNUTIL10] Salience value must be an integer value.
Salience requires a integer argument and will otherwise result in this error message.

Example:
CLIPS> (defrule error (declare (salience a)) =>)

[PRNUTIL11] The fact <fact-id> has been retracted.
This error occurs when a function expecting a fact address argument is provided a retracted fact.

Example:
CLIPS> (bind ?f (assert (a b c)))
<Fact-1>
CLIPS> (retract ?f)
CLIPS> (fact-index ?f)

[PRNUTIL12] The variable/slot reference ?<variable>:<slot> cannot be resolved because
the referenced fact <fact-id> has been retracted.
This error occurs when using shorthand slot notation with a retracted fact.

Example:
CLIPS> (deftemplate point (slot x) (slot y))
CLIPS> (assert (point (x 1) (y 2)))
<Fact-1>

```
CLIPS Basic Programming Guide 385
```

```
CLIPS> (do-for-fact ((?p point)) TRUE (retract ?p) (+ ?p:x ?p:y))
```

[PRNUTIL13] The variable/slot reference ?<variable>:<slot> is invalid because the
referenced fact <fact-id> does not contain the specified slot.
This error occurs when using shorthand slot notation for a fact that does not contain the specified
slot.

Example:
CLIPS> (deftemplate point (slot x) (slot y))
CLIPS> (assert (point (x 1) (y 2)))
<Fact-1>
CLIPS> (do-for-fact ((?p point)) TRUE (+ ?p:x ?p:z))

[PRNUTIL14] The variable/slot reference ?<variable>:<slot> is invalid because slot names
must be symbols.
This error occurs when using shorthand slot notation with a non-symbolic slot name.

Example:
CLIPS> (deftemplate point (slot x) (slot y))
CLIPS> (do-for-fact ((?p point)) TRUE (+ ?p:x ?p:37))

[PRNUTIL15] The variable/slot reference ?<variable>:<slot> cannot be resolved because
the referenced instance <instance-name> has been deleted.
This error occurs when using shorthand slot notation with a deleted instance.

Example:
CLIPS> (defclass POINT (is-a USER) (slot x) (slot y))
CLIPS> (make-instance p1 of POINT (x 1) (y 2))
[p1]
CLIPS> (do-for-all-instances ((?p POINT)) TRUE (send ?p delete) (+ ?p:x ?p:y))

[PRNUTIL16] The variable/slot reference ?<variable>:<slot> is invalid because the
referenced instance <instance-name> does not contain the specified slot.
This error occurs when using shorthand slot notation for an instance that does not contain the
specified slot.

Example:
CLIPS> (defclass POINT (is-a USER) (slot x) (slot y))
CLIPS> (make-instance p1 of POINT (x 1) (y 2))
[p1]
CLIPS> (do-for-all-instances ((?p POINT)) TRUE (+ ?p:x ?p:z))

[ROUTER1] Logical name <logical_name> was not recognized by any routers
This error results because "Hello" is not recognized as a valid router name.

Example:
CLIPS> (printout "Hello" crlf)

```
386 Appendix F: CLIPS Error Messages
```

[RULECSTR1] Variable <variable name> in CE #<integer> slot <slot name> has
constraint conflicts which make the pattern unmatchable.
or
[RULECSTR1] Variable <variable name> in CE #<integer> field #<integer> has constraint
conflicts which make the pattern unmatchable.
or
[RULECSTR1] CE #<integer> slot <slot name> has constraint conflicts which make the
pattern unmatchable.
or
[RULECSTR1] CE #<integer> field #<integer> has constraint conflicts which make the
pattern unmatchable.
This error occurs when slot value constraints (such as allowed types) prevents any value from
matching the slot constraint for a pattern.

Example:
CLIPS> (deftemplate machine (slot id (type SYMBOL)))
CLIPS> (deftemplate product (slot id (type INTEGER)))
CLIPS>
(defrule error
(machine (id ?id))
(product (id ?id))
=>)

[RULECSTR2] Previous variable bindings of <variable name> caused the type restrictions
for argument #<integer> of the expression <expression>
found in CE#<integer> slot <slot name> to be violated.
This error occurs when previous variable bindings and constraints prevent a variable from
containing a value which satisfies the type constraints for one of a function’s parameters.

Example:
CLIPS> (deftemplate machine (slot id (type SYMBOL)))
CLIPS>
(defrule error
(machine (id ?id&:(> ?id 3)))
=>)

[RULECSTR3] Previous variable bindings of <variable name> caused the type restrictions
for argument #<integer> of the expression <expression>
found in the rule's RHS to be violated.
This error occurs when previous variable bindings and constraints prevent a variable from
containing a value which satisfies the type constraints for one of a function’s parameters.

Example:
CLIPS> (deftemplate machine (slot id (type SYMBOL)))
CLIPS>
(defrule error

```
CLIPS Basic Programming Guide 387
```

```
(machine (id ?id))
=>
(println (+ ?id 1)))
```

[RULELHS1] The logical CE cannot be used with a not/exists/forall CE.
Logical CEs can be placed outside, but not inside, a not/exists/forall CE.

Example:
CLIPS> (defrule error (not (logical (machine))) =>)

[RULELHS2] A pattern CE cannot be bound to a pattern-address within a not CE
This is an illegal operation and results in an error message.

Example:
CLIPS> (defrule error (not ?m <- (machine)) =>)

[RULEPSR1] Logical CEs must be placed first in a rule
If logical CEs are used, then the first CE must be a logical CE.

Example:
CLIPS> (defrule error (machine) (logical (product)) =>)

[RULEPSR2] Gaps may not exist between logical CEs
Logical CEs found within a rule must be contiguous.

Example:
CLIPS> (defrule error (logical (machine)) (product) (logical (order)) =>)

[STRNGFUN1] Function build does not work in run time modules.
The build function does not work in run time modules because the code required for parsing is not
available.

[STRNGFUN2] Function '<function>' encountered extraneous input.
The 'eval' and 'build' cannot contain additional input after the first command or construct that is
parsed.

Example:
CLIPS> (eval "(+ 2 3) (\* 4 5)")

[SYSDEP1] No file found for <option> option.
This message occurs if the –f, -f2, or -l option is used when executing CLIPS, but no arguments
are provided.

Example:
clips –f

```
388 Appendix F: CLIPS Error Messages
```

[SYSDEP2] Invalid option <option>.
This message occurs if an invalid option is used.

Example:
clips –f3

[TEXTPRO1] Could not open file <file-name>.
This error occurs when the external text-processing system command fetch encounters an error
when loading a file.

Example:
CLIPS> (fetch "invalid.txt")

[TEXTPRO2] File <file-name> already loaded.
This error occurs when the external text-processing system command fetch encounters an error
when loading a file.

Example:
CLIPS> (fetch "file.txt")
CLIPS> (fetch "file.txt")

[TEXTPRO3] No entries found.
or
[TEXTPRO4] Line <number> : Previous entry not closed.
or
[TEXTPRO5] Line <number> : Invalid delimeter string.
or
[TEXTPRO6] Line <number> : Invalid entry type.
or
[TEXTPRO7] Line <number> : Non-menu entries cannot have subtopics.
or
[TEXTPRO8] Line <number> : Unmatched end marker.
These errors occurs when a file is fetched with invalid entries.

[TMPLTDEF1] Invalid slot <slot name> not defined in corresponding deftemplate
<deftemplate name>
The slot name supplied does not correspond to a slot name defined in the corresponding
deftemplate

Example:
CLIPS> (deftemplate machine (slot id))
CLIPS> (defrule error (machine (manufacturer Acme)) =>)

```
CLIPS Basic Programming Guide 389
```

[TMPLTDEF2] The single field slot <slot name> can only contain a single field value.
If a slot definition is specified in a template pattern or fact, the contents of the slot must be capable
of matching against or evaluating to a single value.

Example:
CLIPS> (deftemplate machine (slot id))
CLIPS> (assert (machine (id)))

[TMPLTFUN 1 ] Attempted to assert a multifield value into the single field slot <slot name>
of deftemplate <deftemplate name>.
A multifield value cannot be stored in a single field slot.

Example:
CLIPS> (deftemplate machine (slot id))
CLIPS>
(defrule error
=>
(bind ?id (create$ 34 890))
(assert (machine (id ?id))))
CLIPS> (run)

[TMPLTRHS1] Slot <slot name> requires a value because of its (default ?NONE) attribute.
The (default ?NONE) attribute requires that a slot value be supplied whenever a new fact is created.

Example:
CLIPS> (deftemplate machine (slot id (default ?NONE)))
CLIPS> (assert (machine))

```
390 Appendix G: CLIPS BNF
```

## Appendix G: CLIPS BNF

Data Types

```
<symbol> ::= A valid symbol as specified
in section 2.3.1
```

```
<string> ::= A valid string as specified
in section 2.3.1
```

```
<float> ::= A valid float as specified
in section 2.3.1
```

```
<integer> ::= A valid integer as specified
in section 2.3.1
```

```
<instance-name> ::= A valid instance-name as specified
in section 2.3.1
```

```
<number> ::= <float> | <integer>
```

```
<lexeme> ::= <symbol> | <string>
```

```
<constant> ::= <symbol> | <string> | <integer> |
<float> | <instance-name>
```

```
<comment> ::= <string>
```

```
<variable-symbol> ::= A symbol beginning with an
alphabetic character
```

```
<function-name> ::= Any symbol which corresponds to a
system or user defined function, a
deffunction name, or a defgeneric
name
```

```
<file-name> ::= A symbol or string which is a valid
file name (including path
information) for the operating
system under which CLIPS is running
```

```
<slot-name> ::= A valid deftemplate slot name
```

```
<...-name> ::= A <symbol> where the ellipsis
indicate what the symbol represents.
For example, <rule-name> is a symbol
which represents the name of a rule.
```

```
CLIPS Basic Programming Guide 391
```

Variables and Expressions

```
<single-field-variable> ::= ?<variable-symbol>
```

```
<multifield-variable> ::= $?<variable-symbol>
```

```
<global-variable> ::= ?*<symbol>*
```

```
<variable> ::= <single-field-variable> |
<multifield-variable> |
<global-variable>
```

```
<function-call> ::= (<function-name> <expression>*)
```

```
<expression> ::= <constant> | <variable> |
<function-call>
```

```
<action> ::= <expression>
```

```
<...-expression> ::= An <expression> which returns
the type indicated by the
ellipsis. For example,
<integer-expression> should
return an integer.
```

Constructs

```
<CLIPS-program> ::= <construct>*
```

```
<construct> ::= <deffacts-construct> |
<deftemplate-construct> |
<defglobal-construct> |
<defrule-construct> |
<deffunction-construct> |
<defgeneric-construct> |
<defmethod-construct> |
<defclass-construct> |
<definstance-construct> |
<defmessage-handler-construct> |
<defmodule-construct>
```

Deffacts Construct

```
<deffacts-construct> ::= (deffacts <deffacts-name> [<comment>]
<RHS-pattern>*)
```

Deftemplate Construct

```
<deftemplate-construct>
::= (deftemplate <deftemplate-name>
[<comment>]
<slot-definition>*)
```

```
392 Appendix G: CLIPS BNF
```

```
<slot-definition> ::= <single-slot-definition> |
<multislot-definition>
```

```
<single-slot-definition>
::= (slot <slot-name> <template-attribute>*)
```

```
<multislot-definition>
::= (multislot <slot-name>
<template-attribute>*)
```

```
<template-attribute>
::= <default-attribute> |
<constraint-attribute>
```

```
<default-attribute>
::= (default ?DERIVE | ?NONE | <expression>*) |
(default-dynamic <expression>*)
```

Fact Specification

```
<RHS-pattern> ::= <ordered-RHS-pattern> |
<template-RHS-pattern>
```

```
<ordered-RHS-pattern> ::= (<symbol> <RHS-field>+)
```

```
<template-RHS-pattern> ::= (<deftemplate-name> <RHS-slot>*)
```

```
<RHS-slot> ::= <single-field-RHS-slot> |
<multifield-RHS-slot>
```

```
<single-field-RHS-slot> ::= (<slot-name> <RHS-field>)
```

```
<multifield-RHS-slot> ::= (<slot-name> <RHS-field>*)
```

```
<RHS-field> ::= <variable> |
<constant> |
<function-call>
```

Defrule Construct

```
<defrule-construct> ::= (defrule <rule-name> [<comment>]
[<declaration>]
<conditional-element>*
=>
<action>*)
```

```
<declaration> ::= (declare <rule-property>+)
```

```
<rule-property> ::= (salience <integer-expression>) |
(auto-focus <boolean-symbol>)
```

```
<boolean-symbol> ::= TRUE | FALSE
```

```
<conditional-element> ::= <pattern-CE> |
```

CLIPS Basic Programming Guide 393

```
<assigned-pattern-CE> |
<not-CE> | <and-CE> | <or-CE> |
<logical-CE> | <test-CE> |
<exists-CE> | <forall-CE>
```

```
<pattern-CE> ::= <ordered-pattern-CE> |
<template-pattern-CE> |
<object-pattern-CE>
```

```
<assigned-pattern-CE> ::= <single-field-variable> <- <pattern-CE>
```

```
<not-CE> ::= (not <conditional-element>)
```

```
<and-CE> ::= (and <conditional-element>+)
```

```
<or-CE> ::= (or <conditional-element>+)
```

```
<logical-CE> ::= (logical <conditional-element>+)
```

```
<test-CE> ::= (test <function-call>)
```

```
<exists-CE> ::= (exists <conditional-element>+)
```

```
<forall-CE> ::= (forall <conditional-element>
<conditional-element>+)
```

```
<ordered-pattern-CE> ::= (<symbol> <constraint>*)
```

```
<template-pattern-CE> ::= (<deftemplate-name> <LHS-slot>*)
```

```
<object-pattern-CE> ::= (object <attribute-constraint>*)
```

```
<attribute-constraint> ::= (is-a <constraint>) |
(name <constraint>) |
(<slot-name> <constraint>*)
```

```
<LHS-slot> ::= <single-field-LHS-slot> |
<multifield-LHS-slot>
```

```
<single-field-LHS-slot> ::= (<slot-name> <constraint>)
```

```
<multifield-LHS-slot> ::= (<slot-name> <constraint>*)
```

```
<constraint> ::=? | $? | <connected-constraint>
```

```
<connected-constraint>
::= <single-constraint> |
<single-constraint> & <connected-constraint> |
<single-constraint> | <connected-constraint>
```

```
<single-constraint> ::= <term> | ~<term>
```

```
<term> ::= <constant> |
<single-field-variable> |
```

```
394 Appendix G: CLIPS BNF
```

```
<multifield-variable> |
:<function-call> |
=<function-call>
```

Defglobal Construct

```
<defglobal-construct> ::= (defglobal [<defmodule-name>]
<global-assignment>*)
```

```
<global-assignment> ::= <global-variable> = <expression>
```

```
<global-variable> ::= ?*<symbol>*
```

Deffunction Construct

```
<deffunction-construct>
::= (deffunction <name> [<comment>]
(<regular-parameter>* [<wildcard-parameter>])
<action>*)
```

```
<regular-parameter> ::= <single-field-variable>
```

```
<wildcard-parameter> ::= <multifield-variable>
```

Defgeneric Construct

```
<defgeneric-construct> ::= (defgeneric <name> [<comment>])
```

Defmethod Construct

```
<defmethod-construct>
::= (defmethod <name> [<index>] [<comment>]
(<parameter-restriction>*
[<wildcard-parameter-restriction>])
<action>*)
```

```
<parameter-restriction>
::= <single-field-variable> |
(<single-field-variable> <type>* [<query>])
```

```
<wildcard-parameter-restriction>
::= <multifield-variable> |
(<multifield-variable> <type>* [<query>])
```

```
<type> ::= <class-name>
```

```
<query> ::= <global-variable> | <function-call>
```

Defclass Construct

```
<defclass-construct> ::= (defclass <name> [<comment>]
(is-a <superclass-name>+)
```

```
CLIPS Basic Programming Guide 395
```

```
[<role>]
[<pattern-match-role>]
<slot>*
<handler-documentation>*)
```

```
<role> ::= (role concrete | abstract)
```

```
<pattern-match-role>
::= (pattern-match reactive | non-reactive)
```

```
<slot> ::= (slot <name> <facet>*) |
(single-slot <name> <facet>*) |
(multislot <name> <facet>*)
```

```
<facet> ::= <default-facet> | <storage-facet> |
<access-facet> | <propagation-facet> |
<source-facet> | <pattern-match-facet> |
<visibility-facet> | <create-accessor-facet>
<override-message-facet> | <constraint-attribute>
```

```
<default-facet> ::=
(default ?DERIVE | ?NONE | <expression>*) |
(default-dynamic <expression>*)
```

```
<storage-facet> ::= (storage local | shared)
```

```
<access-facet>
::= (access read-write | read-only | initialize-only)
```

```
<propagation-facet> ::= (propagation inherit | no-inherit)
```

```
<source-facet> ::= (source exclusive | composite)
```

```
<pattern-match-facet>
::= (pattern-match reactive | non-reactive)
```

```
<visibility-facet> ::= (visibility private | public)
```

```
<create-accessor-facet>
::= (create-accessor ?NONE | read | write | read-write)
```

```
<override-message-facet>
::= (override-message ?DEFAULT | <message-name>)
```

```
<handler-documentation>
::= (message-handler <name> [<handler-type>])
```

```
<handler-type> ::= primary | around | before | after
```

Defmessage-handler Construct

```
<defmessage-handler-construct>
::= (defmessage-handler <class-name>
<message-name> [<handler-type>] [<comment>]
```

```
396 Appendix G: CLIPS BNF
```

```
(<parameter>* [<wildcard-parameter>])
<action>*)
```

```
<handler-type> ::= around | before | primary | after
```

```
<parameter> ::= <single-field-variable>
```

```
<wildcard-parameter> ::= <multifield-variable>
```

Definstances Construct

```
<definstances-construct>
::= (definstances <definstances-name>
[active] [<comment>]
<instance-template>*)
```

```
<instance-template> ::= (<instance-definition>)
```

```
<instance-definition> ::= <instance-name-expression> of
<class-name-expression>
<slot-override>*
```

```
<slot-override> ::= (<slot-name-expression> <expression>*)
```

Defmodule Construct

```
<defmodule-construct> ::= (defmodule <module-name> [<comment>]
<port-specification>*)
```

```
<port-specification> ::= (export <port-item>) |
(import <module-name> <port-item>)
```

```
<port-item> ::= ?ALL |
?NONE |
<port-construct> ?ALL |
<port-construct> ?NONE |
<port-construct> <construct-name>+
```

```
<port-construct> ::= deftemplate | defclass |
defglobal | deffunction |
defgeneric
```

Constraint Attributes

```
<constraint-attribute>
::= <type-attribute> |
<allowed-constant-attribute> |
<range-attribute> |
<cardinality-attribute>
```

```
<type-attribute> ::= (type <type-specification>)
```

```
<type-specification> ::= <allowed-type>+ | ?VARIABLE
```

CLIPS Basic Programming Guide 397

```
<allowed-type> ::= SYMBOL | STRING | LEXEME |
INTEGER | FLOAT | NUMBER |
INSTANCE-NAME | INSTANCE-ADDRESS |
INSTANCE | EXTERNAL-ADDRESS |
FACT-ADDRESS
```

```
<allowed-constant-attribute>
::= (allowed-symbols <symbol-list>) |
(allowed-strings <string-list>) |
(allowed-lexemes <lexeme-list> |
(allowed-integers <integer-list>) |
(allowed-floats <float-list>) |
(allowed-numbers <number-list>) |
(allowed-instance-names <instance-list>) |
(allowed-classes <class-name-list>) |
(allowed-values <value-list>)
```

```
<symbol-list> ::= <symbol>+ | ?VARIABLE
```

```
<string-list> ::= <string>+ | ?VARIABLE
```

```
<lexeme-list> ::= <lexeme>+ | ?VARIABLE
```

```
<integer-list> ::= <integer>+ | ?VARIABLE
```

```
<float-list> ::= <float>+ | ?VARIABLE
```

```
<number-list> ::= <number>+ | ?VARIABLE
```

```
<instance-name-list> ::= <instance-name>+ | ?VARIABLE
```

```
<class-name-list> ::= <class-name>+ | ?VARIABLE
```

```
<value-list> ::= <constant>+ | ?VARIABLE
```

```
<range-attribute> ::= (range <range-specification>
<range-specification>)
```

```
<range-specification> ::= <number> | ?VARIABLE
```

```
<cardinality-attribute>
::= (cardinality <cardinality-specification>
<cardinality-specification>)
```

```
<cardinality-specification>
::= <integer> | ?VARIABLE
```

```
398 Appendix H: Reserved Function Names
```

## Appendix H: Reserved Function Names

This appendix lists all of the functions provided by either standard CLIPS or various CLIPS
extensions. They should be considered reserved function names, and users should not create
user-defined functions with any of these names.

!=

- \*\*

*

- /
  <
  <=
  <>
  =
  > =
  > abs
  > acos
  > acosh
  > acot
  > acoth
  > acsc
  > acsch
  > active-duplicate-instance
  > active-initialize-instance
  > active-make-instance
  > active-message-duplicate-instance
  > active-message-modify-instance
  > active-modify-instance
  > agenda
  > and
  > any-instancep
  > apropos
  > asec
  > asech
  > asin
  > asinh

```
assert
assert-string
atan
atanh
batch
batch*
bind
bload
bload-facts
bload-instances
break
browse-classes
bsave
bsave-facts
bsave-instances
build
call-next-handler
call-next-method
call-specific-method
chdir
class
class-abstractp
class-existp
class-reactivep
class-slots
class-subclasses
class-superclasses
clear
clear-error
clear-focus-stack
close
conserve-mem
constructs-to-c
```

```
CLIPS Basic Programming Guide 399
```

cos
cosh
cot
coth
create$
csc
csch
defclass-module
deffacts-module
deffunction-module
defgeneric-module
defglobal-module
definstances-module
defrule-module
deftemplate-module
deg-grad
deg-rad
delayed-do-for-all-instances
delete$
delete-instance
dependencies
dependents
describe-class
difference$
div
do-for-all-instances
do-for-instance
dribble-off
dribble-on
duplicate
duplicate-instance
duplicate-instance
dynamic-get
dynamic-put
edit
eq
eval
evenp
exit
exp
expand$
explode$

```
fact-existp
fact-index
fact-relation
fact-slot-names
fact-slot-value
facts
fetch
find-all-instances
find-instance
first$
float
floatp
flush
focus
foreach
format
gensym
gensym*
get
get-current-module
get-defclass-list
get-deffacts-list
get-deffunction-list
get-defgeneric-list
get-defglobal-list
get-definstances-list
get-defmessage-handler-list
get-defmethod-list
get-defmodule-list
get-defrule-list
get-deftemplate-list
get-dynamic-constraint-checking
get-error
get-fact-duplication
get-fact-list
get-focus
get-focus-stack
get-function-restrictions
get-method-restrictions
get-reset-globals
get-salience-evaluation
get-sequence-operator-recognition
```

```
400 Appendix H: Reserved Function Names
```

get-strategy
gm-time
grad-deg
halt
if
implode$
init-slots
initialize-instance
initialize-instance
insert$
instance-address
instance-addressp
instance-existp
instance-name
instance-name-to-symbol
instance-namep
instancep
instances
integer
integer
intersection$
length$
lexemep
list-defclasses
list-deffacts
list-deffunctions
list-defgenerics
list-defglobals
list-definstances
list-defmessage-handlers
list-defmethods
list-defmodules
list-defrules
list-deftemplates
list-focus-stack
list-watch-items
load
load\*
load-facts
load-instances
local-time
log
log10

```
loop-for-count
lowcase
make-instance
make-instance
matches
max
mem-requests
mem-used
member$
message-duplicate-instance
message-duplicate-instance
message-handler-existp
message-modify-instance
message-modify-instance
min
mod
modify
modify-instance
modify-instance
multifieldp
neq
next-handlerp
next-methodp
not
nth$
numberp
object-pattern-match-delay
oddp
open
operating-system
options
or
override-next-handler
override-next-method
pi
pointerp
pop-focus
ppdefclass
ppdeffacts
ppdeffunction
ppdefgeneric
ppdefglobal
ppdefinstances
```

```
CLIPS Basic Programming Guide 401
```

ppdefmessage-handler
ppdefmethod
ppdefmodule
ppdefrule
ppdeftemplate
ppinstance
preview-generic
preview-send
primitives-info
print
println
print-region
printout
progn
progn$
put
rad-deg
random
read
readline
refresh
refresh-agenda
release-mem
remove
remove-break
rename
replace$
reset
rest$
restore-instances
retract
return
rewind
round
rule-complexity
rules
run
save
save-facts
save-instances
sec
sech

```
seed
seek
send
set-break
set-current-module
set-dynamic-constraint-checking
set-error
set-fact-duplication
set-reset-globals
set-salience-evaluation
set-sequence-operator-recognition
set-strategy
setgen
show-breaks
show-defglobals
show-fht
show-fpn
show-joins
show-opn
sin
sinh
slot-allowed-values
slot-cardinality
slot-delete$
slot-direct-accessp
slot-direct-delete$
slot-direct-insert$
slot-direct-replace$
slot-existp
slot-facets
slot-initablep
slot-insert$
slot-publicp
slot-range
slot-replace$
slot-sources
slot-types
slot-writablep
sqrt
str-assert
str-cat
str-compare
```

```
402 Appendix H: Reserved Function Names
```

str-index
str-length
stringp
sub-string
subclassp
subseq$
subsetp
superclassp
switch
sym-cat
symbol-to-instance-name
symbolp
system
tan
tanh
tell
time
toss
type
type
undefclass
undeffacts
undeffunction
undefgeneric
undefglobal
undefinstances
undefmessage-handler
undefmethod
undefrule
undeftemplate
unget-char
union$
unmake-instance
unwatch
upcase
void
watch
while

```
CLIPS Basic Programming Guide 403
```

## Index

- .............................................................................. 200
  : ................................................................................. 41
  ? .................................................................................. 6
  ?DERIVE ................................................................. 19
  ?NONE ..................................................................... 19
  ?self ................................................................113, 114
  ( .................................................................................. 6
  ) .................................................................................. 6

* .............................................................................. 200
  \*\* ............................................................................ 207
  / ............................................................................... 201
  & ...........................................................................6, 38

- ............................................................................. 199
  < .........................................................................6, 169
  <= ........................................................................... 169
  <> ........................................................................... 167
  = ....................................................................... 44 , 166
  => ............................................................................. 24
  > ............................................................................. 168
  > = ........................................................................... 168
  > | .............................................................................6, 38
  > ~............................................................................6, 38
  > $? ................................................................................ 6
  > abs .......................................................................... 202
  > abstraction ................................................................ 16
  > action ..........................................................14, 24, 163
  > activated ................................................................... 26
  > active-duplicate-instance ..........................87, 120, 134
  > active-initialize-instance ..................................87, 128
  > active-make-instance ................................87, 125 , 127
  > active-message-duplicate-instance ...........87, 121, 136
  > active-message-modify-instance ..............87, 120, 133
  > active-modify-instance .............................87, 119, 132
  > Ada .............................................................6, 8, 13, 14
  > Advanced Programming Guide ................xv, 2, 6, 185
  > agenda ..........................................26, 30, 67, 302, 303

```
allowed-classes ...................................................... 157
ampersand .................................................................. 6
and ......................................................................... 170
antecedent ................................................................ 14
any-factp ................................................................ 244
any-instancep ................................................... 87, 143
apropos .................................................................. 287
arrow ........................................................................ 24
assert .................... 10, 19, 87, 221, 230 , 234, 279, 334
assert-string ........................................................... 234
atan2 .............................................................. 204 , 333
attribute
default ............................................................... 19
auto-focus ................................................................ 68
backslash ........................................... 6, 186, 193, 234
Basic Programming Guide ...................................... xv
batch .................................................................. 4, 285
batch* ................................................................ 4, 285
bind ...................................... 36, 70, 87, 115, 130, 209
bload .............................................................. 283 , 286
bload-facts ............................................. 294, 295 , 334
bload-instances .............................................. 320, 321
break ................................ 87, 143, 212, 213, 215 , 243
browse-classes ....................................................... 315
bsave ...................................................... 156, 283, 284
bsave-facts ............................................. 294 , 295, 334
bsave-instances ...................................... 320 , 321, 334
build ....................................................................... 181
C .............................................. 6, 8, 11, 13, 14, 15, 18
call-next-handler .............................. 87, 122, 123, 268
call-next-method ................................ 87, 90, 254 , 255
call-specific-method ............................ 79, 87, 90, 255
carriage return............................................................ 6
case sensitive ............................................................. 6
chdir ............................................................... 199 , 333
check-syntax .......................................................... 183
```

```
404 Index
```

class ........................................7, 12 , 82, 271, 312, 315
abstract ........................................93, 98 , 266, 312
concrete ..................................................... 98 , 266
existence .......................................................... 257
immediate .................................................. 98 , 111
non-reactive....................................................... 98
precedence......................................................... 95
reactive ...................................................... 98 , 266
specific ........................................ 95 , 98, 104, 123
system ............................................................... 92
ADDRESS ................................................. 92
EXTERNAL-ADDRESS ........................... 92
FACT-ADDRESS...................................... 92
FLOAT ...................................................... 92
INSTANCE................................................ 92
INSTANCE-ADDRESS ............................ 92
INSTANCE-NAME .................................. 92
INTEGER .................................................. 92
LEXEME ................................................... 92
MULTIFIELD ........................................... 92
NUMBER .................................................. 92
OBJECT ....................................... 92 , 95, 315
PRIMITIVE ............................................... 92
STRING ..................................................... 92
SYMBOL ................................................... 92
USER ................... 92 , 95, 117, 128, 270, 319
user-defined...........................................7, 12, 318
class function ..................................................253, 271
class-abstractp ........................................................ 260
class-existp ............................................................. 257
class-reactivep ........................................................ 260
class-slots ............................................................... 261
class-subclasses ...................................................... 260
class-superclasses ................................................... 260
clear ............................10, 70, 148, 150, 155, 283, 284
clear-error ....................................................... 223 , 333
clear-focus-stack .................................................... 304
CLOS..................................................................79, 92
close................................................................ 187 , 197
command ........................................................ 163 , 282
comment .................................................................6, 9
condition ................................................................... 14
conditional element ................................ 14 , 24, 30, 66

```
and ........................................................ 24, 30, 53
exists ........................................................... 30, 56
forall ........................................................... 30, 58
logical ......................................................... 30, 60
not ............................................................... 30, 54
or ................................................................ 30, 52
pattern ................................................... 24, 30, 31
literal ......................................................... 31
test ........................................................ 27, 30, 50
conflict resolution strategy ................ 14, 26 , 284, 303
breadth .............................................................. 27
complexity ........................................................ 27
depth ................................................................. 27
lex ..................................................................... 28
mea ................................................................... 29
random.............................................................. 29
simplicity .......................................................... 27
consequent ............................................................... 14
conservation........................................................... 266
conserve-mem ............................................... 283, 323
constant .................................................................. 2, 7
constraint ............................................... 30, 31, 38 , 41
connective .................................................. 31, 38
field .................................................................. 31
literal ................................................................ 31
predicate ............................................... 31, 41 , 50
return value................................................. 31, 44
construct ........................................................ 2, 9 , 180
constructs ............................................................... 329
constructs-to-c ....................................................... 286
convenience ........................................................... 266
COOL ............................ 7, 13, 16, 17, 79, 82, 92 , 253
create$ ................................................................... 170
crlf ......................................................................... 188
daemon .................................................. 117 , 125, 141
deactivated ............................................................... 26
declarative technique ............................... 90 , 111 , 123
declare ..................................................................... 66
default-dynamic ....................................................... 19
defclass .................................................... 7, 9, 94 , 110
defclass-module ..................................................... 257
deffacts .................................................. 9, 12 , 22 , 296
deffacts-module ..................................................... 248
```

```
CLIPS Basic Programming Guide 405
```

deffunction ................................... 8 , 9, 15, 76 , 79, 307
action ................................................................. 77
advantages over generic functions .................. 347
execution error .................................................. 77
recursion ............................................................ 77
regular parameter .............................................. 76
return value ....................................................... 77
wildcard parameter............................................ 76
deffunction-module ................................................ 251
defgeneric ...................................................8, 9, 79 , 80
defgeneric-module.................................................. 252
defglobal .................................................9, 13 , 70 , 305
defglobal-module ................................................... 251
definstances ..........................................9, 13 , 127 , 317
definstances-module ............................................... 269
defmessage-handler ....................................9, 110, 316
defmethod ...................................................8, 9, 79 , 80
defmodule ...................................................9, 148 , 321
defmodules ............................................................... 16
defrule ..........................................................9, 24 , 297
defrule-module ....................................................... 249
deftemplate .............................................9, 11 , 18 , 291
deftemplate fact .................................................. 11 , 18
deftemplate-module................................................ 224
deftemplate-slot-allowed-values ............................ 225
deftemplate-slot-cardinality ................................... 225
deftemplate-slot-defaultp ....................................... 225
deftemplate-slot-default-value ............................... 226
deftemplate-slot-existp ........................................... 227
deftemplate-slot-multip .......................................... 227
deftemplate-slot-names .......................................... 228
deftemplate-slot-range............................................ 228
deftemplate-slot-singlep ......................................... 229
deftemplate-slot-types ............................................ 229
deg-grad.................................................................. 205
deg-rad.................................................................... 205
delayed-do-for-all-facts ............................87, 243, 246
delayed-do-for-all-instances .....................87, 143, 146
delete$ ............................................................ 172 , 173
delete-instance ................................................130, 271
delete-member$ ...................................................... 177
delimiter ..................................................................... 6

```
dependencies ................................................. 301 , 336
dependents ..................................................... 302 , 336
describe-class................................................... 95, 312
difference$ ..................................................... 178 , 336
direct-insert$ .......................................................... 275
direct-mv-delete..................................................... 336
direct-mv-insert ..................................................... 336
direct-mv-replace................................................... 336
div .......................................................................... 201
do-for-all-facts ......................................... 87, 243, 246
do-for-all-instances .......................... 87, 143, 145 , 146
do-for-fact ................................................ 87, 243, 245
do-for-instance......................................... 87, 143, 145
double quote .............................................................. 6
dribble-off .............................................................. 288
dribble-on .............................................................. 287
duplicate ................ 10, 12, 20, 87, 233 , 279, 334, 336
duplicate-instance .................................... 87, 120, 134
dynamic binding ...................................................... 16
dynamic-get ........................................... 129, 273 , 377
dynamic-put ........................................... 130, 274 , 377
encapsulation ..................................... 16 , 92, 114, 125
EOF ....................................................... 189 , 190 , 196
eq ........................................................................... 166
eval ................................................................ 180 , 334
evenp ..................................................................... 165
exit ............................................................. 3, 187, 284
exp ......................................................................... 207
expand$ ................................................... 87, 113, 279
explode$ ........................................................ 173 , 334
exponential notation .................................................. 5
exporting constructs .............................................. 151
expression .................................................................. 9
external-address ................................................. 5, 6 , 7
external-addressp ........................................... 165 , 335
```

- f ................................................................................ 3
- f2 .............................................................................. 4
  facet ........................................................... 94, 99 , 312
  access
  initialize-only .......................................... 102
  read-only ................................................. 102
  read-write ................................................ 102

```
406 Index
```

create-accessor ................................ 107 , 108, 266
?NONE .................................................... 107
read .......................................................... 107
read-write ................................................. 107
write ......................................................... 107
default ............................................................... 99
default-dynamic ................................................ 99
multislot ............................................................ 99
override-message ............................................ 108
pattern-match
non-reactive ............................................. 105
reactive ..................................................... 105
propagation
inherit ....................................................... 104
no-inherit............................................98, 104
shared ................................................................ 99
slot ..................................................................... 99
source
composite ...........................................98, 104
exclusive .................................................. 104
storage
local.......................................................... 101
shared ....................................................... 101
visibility .......................................................... 106
private ...................................................... 106
public ....................................................... 106
fact ................................................................ 10 , 12, 22
fact identifier ............................................................ 10
fact-address ........................................5, 7, 10 , 49, 240
fact-existp ............................................................... 235
fact-index............ 10 , 20, 231, 232, 233, 235 , 302, 336
fact-list.................................................... 10 , 12, 22, 24
fact-relation .................................................... 236 , 336
facts ........................................................................ 292
fact-set .................................................................... 240
action ............................................................... 242
distributed action ............................................. 242
member ........................................................... 240
member variable...................................... 240 , 242
query ....................................................... 241 , 242
query execution error ...................................... 243
query functions................................................ 243
template ........................................................... 240

```
template restriction ......................................... 240
fact-slot-names .............................................. 236 , 336
fact-slot-value ................................................ 237 , 336
FALSE ..................................................................... 41
fetch ....................................................................... 325
ff ............................................................................ 188
field ................................................................ 7 , 10, 11
find-all-facts .................................................... 88, 245
find-all-instances ............................................. 87, 144
find-fact ........................................................... 87, 244
find-instance .................................................... 87, 144
fire ........................................................................... 24
first$....................................................................... 176
float ................................................................ 5, 7, 203
floatp ...................................................................... 164
flush ............................................................... 197 , 333
focus .................................................. 26, 68, 155, 303
foreach ............................................. 87, 215, 216 , 279
format ............................................................ 191 , 196
FORTRAN ................................................................ 8
funcall ............................................................ 221 , 334
function .......................................... 8 , 15, 79, 142, 163
call .................................................................. 2, 8
external ............................................................. 36
predicate ........................................... 41 , 163, 272
reserved names ............................................... 398
system defined ............................................ 8 , 398
user defined ............................................ 6, 8 , 383
generic dispatch ............................. 79 , 80, 83, 85 , 347
generic function ................................... 13, 15, 79 , 308
disadvantages ................................................. 347
header ......................................................... 80, 81
order dependence ............................................. 80
ordering of method parameter restrictions ..... 347
performance penalty ......................................... 80
return value....................................................... 91
gensym........................................................... 217 , 218
gensym*................................................. 126, 134, 218
get-auto-float-dividend .......................................... 336
get-char .................................................................. 194
get-class-defaults-mode ......................................... 267
get-current-module ................................................ 277
get-defclass-list ...................................................... 257
```

```
CLIPS Basic Programming Guide 407
```

get-deffacts-list ....................................................... 247
get-deffunction-list ................................................. 251
get-defgeneric-list .................................................. 252
get-defglobal-list .................................................... 251
get-definstances-list................................................ 269
get-defmessage-handler-list ................................... 261
get-defmethod-list .................................................. 252
get-defmodule-list .................................................. 276
get-defrule-list ........................................................ 248
get-deftemplate-list ................................................ 230
get-dynamic-constraint-checking ........................... 287
get-error .................................................................. 223
get-error .................................................................. 333
get-fact-duplication ................................................ 296
get-fact-list ............................................................. 237
get-focus ................................................................. 249
get-focus-stack ....................................................... 249
get-function-restrictions ...................................87, 220
get-incremental-reset .............................................. 336
get-method-restrictions ....................................87, 256
get-profile-percent-threshold.................................. 328
get-region ............................................................... 327
get-reset-globals ..................................................... 307
get-salience-evaluation ........................................... 305
get-sequence-operator-recognition ......................... 280
get-static-constraint-checking ................................ 336
get-strategy ............................................................. 304
gm-time .......................................................... 222 , 333
grad-deg.................................................................. 205
halt .......................................................................... 303
if ...............................................................87, 210 , 279
if portion ................................................................... 14
imperative technique ................................ 90 , 111 , 123
implode$ ......................................................... 173 , 174
importing constructs ............................................... 151
incremental reset ...................................................... 24
inference engine ........................................... 14 , 24, 25
inheritance ..............................................13, 16 , 94, 98
class precedence list. 17 , 94, 95 , 96, 98, 104, 122,
312
class precedence list ........................................ 111
is-a ..................................................................... 95

```
multiple .................................. 13, 17 , 92, 95 , 315
initialize-instance..................... 87, 108, 117, 128 , 270
init-slots ......................................... 117, 126, 128, 270
insert$ .................................................................... 175
instance ............................ 7, 12 , 13 , 98, 101, 312, 318
active ..... 113 , 114, 121, 122, 129, 130, 270, 273,
319
creation ................................................... 121, 125
deletion ........................................................... 118
direct ............................................. 93, 94, 98 , 104
initialization............................ 117, 125, 128, 270
manipulation ................................................... 125
printing ........................................................... 118
instance-address....................... 5, 7 , 49, 271, 272, 348
instance-addressp................................................... 273
instance-existp ....................................................... 273
instance-list ........................................................ 13, 24
instance-name ........................ 5, 7 , 139, 271 , 272, 273
instance-namep ...................................................... 273
instance-name-to-symbol ...................................... 272
instancep ................................................................ 272
instances ................................................................ 319
instance-set ............................................................ 139
action .............................................................. 142
class restriction ............................................... 139
distributed action ............................................ 141
member ........................................................... 139
member variable ..................................... 139 , 142
query ......................................... 17, 141 , 142, 348
query execution error ..................................... 143
query functions ............................................... 143
template .......................................................... 139
integer ............................................................ 5, 7, 203
integerp .................................................................. 164
Interfaces Guide .................................................. xv, 2
intersection$ .................................................. 178 , 336
```

- l................................................................................. 4
  left-hand side ........................................................... 14
  length ..................................................................... 336
  length$ ............................................. 99, 113, 176 , 334
  less than ..................................................................... 6
  lexemep ................................................................. 164

```
408 Index
```

LHS .......................................................................... 24
line feed ...................................................................... 6
list-defclasses ......................................................... 311
list-deffacts ............................................................. 296
list-deffunctions...................................................... 308
list-defgenerics ....................................................... 309
list-defglobals ......................................................... 306
list-definstances ...................................................... 318
list-defmessage-handlers ........................................ 316
list-defmethods .............................81, 87, 88, 309 , 310
list-defmodules ....................................................... 322
list-defrules ............................................................. 297
list-deftemplates ..................................................... 291
list-focus-stack ....................................................... 304
list-watch-items ...................................................... 290
load .............................................4, 282 , 283, 285, 334
load\* ....................................................................... 282
load-facts ................................................ 294 , 295, 334
load-instances ................................................. 320 , 321
local ........................................................................ 293
local-time........................................................ 222 , 333
log ........................................................................... 207
log10 ....................................................................... 208
logical name ................................................... 185 , 287
nil ...188, 191, 291, 292, 296, 297, 305, 307, 308,
311, 316, 318, 321
stdin .........................189, 190, 194, 195, 196, 287
stdout ...............................................187, 191, 287
t .......................187, 189, 190, 191, 194, 195, 196
werror .............................................................. 287
wwarning......................................................... 287
logical support .......................... 61 , 231, 232, 301, 302
loop-for-count ..................................87, 212 , 215, 279
lowcase ................................................................... 182
make-instance ....7, 47, 87, 98, 99, 100, 103, 108, 117,
125 , 127, 270, 320
matches ................................................................... 298
math functions ........................................................ 199
max ......................................................................... 202
member ................................................................... 336
member$ ................................................................. 171
mem-requests ......................................................... 322
mem-used ............................................................... 322

```
message ...... 13, 15, 16, 17, 79, 92, 99, 110, 113, 121,
122, 123, 125 , 126, 128
dispatch .......................................................... 112
execution error ............................... 113, 123, 268
execution error ............................................... 124
implementation ....................................... 110 , 111
return value..................................................... 124
message dispatch ................................................... 121
message-duplicate-instance ............. 87, 108, 121, 135
message-handler. 13, 15, 17, 79, 92, 94, 95, 103, 111 ,
113, 123, 125, 129, 130, 209, 270, 312, 319, 348
action .............................................................. 114
applicability .................... 112, 113, 121, 122 , 317
documentation ................................................ 110
existence ......................................................... 259
forward declaration ........................................ 110
regular parameter ........................................... 112
return value..................................................... 125
shadow.................................................... 123 , 267
specific ........................................... 121, 123, 124
system
create ....................................... 121 , 125, 126
delete ....................... 118 , 126, 127, 130 , 134
direct-duplicate ............................... 120 , 134
direct-modify................................... 119 , 132
init ................... 103, 117 , 125, 126, 128, 270
message-duplicate ................... 120 , 135, 136
message-modify ...................... 120 , 132, 133
print ......................................................... 118
type
after ......................................... 111 , 123, 125
around ............................. 111 , 123, 124, 267
before ...................................... 111 , 123, 125
primary .................................... 111 , 123, 124
wildcard parameter ......................................... 112
message-handler-existp ......................................... 259
message-modify-instance ................ 87, 108, 120, 132
method ................................................... 15, 79 , 80, 92
action ................................................................ 80
applicability ........................................ 83 , 90, 310
execution error ......................................... 91 , 253
explicit .................................................. 79 , 83, 86
implicit ................................................. 79 , 80, 83
```

```
CLIPS Basic Programming Guide 409
```

index .................................................................. 81
parameter query restriction ............................... 82
parameter restriction .................80, 81, 82 , 86, 88
parameter type restriction ................................. 82
precedence.....................................82, 83, 88 , 309
regular parameter ........................................ 82 , 83
return value ....................................................... 91
shadow .............................................. 90 , 253, 317
wildcard parameter............................................ 83
wildcard parameter restriction .......................... 80
min.......................................................................... 202
mod ......................................................................... 209
modify ....................10, 12, 20, 87, 232 , 279, 334, 336
modify-instance ........................................87, 119, 132
module specifier ..................................................... 150
multifield value .......................................................... 7
multifield wildcard ................................................... 33
multifieldp .............................................................. 165
mv-append .............................................................. 336
mv-delete ................................................................ 336
mv-replace .............................................................. 336
mv-slot-delete ......................................................... 336
mv-slot-insert ......................................................... 336
mv-slot-replace ....................................................... 336
mv-subseq .............................................................. 336
neq .......................................................................... 166
next-handlerp....................................................87, 268
next-methodp....................................................87, 253
non-FALSE .............................................................. 41
non-ordered fact ................................................. 11 , 18
not ........................................................................... 170
nth ........................................................................... 336
nth$ ...................................................................99, 171
numberp.................................................................. 163
object ........................................................7, 12 , 15, 16
behavior..................... 12 , 15, 17, 79, 94, 110 , 111
primitive type .................................................... 12
properties................................... 12 , 13, 15, 17 , 94
reference ........................................................ 7 , 17
object-pattern-match-delay ................47, 87, 130 , 279
oddp ........................................................................ 165
off ........................................................................... 329

```
open ............................................... 186 , 187, 197, 198
operating-system ................................................... 222
OPS5 ........................................................................ 28
options ................................................................... 285
or ............................................................................ 170
ordered fact ........................................................ 10 , 18
overload ..................................... 8, 15 , 76, 79 , 80, 347
override-next-handler ...................... 87, 122, 123, 269
override-next-method ........................ 87, 90, 254 , 255
parenthesis ............................................................. 6, 9
pattern ................................................................ 14 , 24
pattern entity ............................................................ 24
pattern-address......................................................... 49
pattern-matching .......................................... 14 , 70, 71
performance ........................................................... 346
pi ............................................................................ 206
pointerp .................................................................. 335
polymorphism .......................................................... 16
pop-focus ............................................................... 250
ppdefclass .............................................................. 311
ppdeffacts .............................................................. 296
ppdeffunction......................................................... 307
ppdefgeneric .......................................................... 308
ppdefglobal ............................................................ 306
ppdefinstances ....................................................... 318
ppdefmessage-handler ........................................... 316
ppdefmethod .......................................................... 308
ppdefmodule .......................................................... 321
ppdefrule ................................................ 150, 283, 297
ppdeftemplate ........................................................ 291
ppfact ............................................................. 293 , 336
ppinstance .............................................................. 319
prefix notation ........................................................... 8
preview-generic ..................................................... 310
preview-send ......................................................... 317
print ............................................................... 188 , 333
println ............................................................ 188 , 333
printout .......................................................... 187 , 191
print-region ............................................................ 325
profile .................................................................... 329
profile-info............................................................. 328
profile-reset ........................................................... 328
```

```
410 Index
```

progn ................................87, 130, 213 , 215, 279, 329
progn$ ......................................87, 214 , 215, 217, 279
quote ........................................................................... 6
rad-deg.................................................................... 206
random.................................................................... 218
read .........................................184, 188 , 190, 285, 335
readline ................................................... 190 , 285, 335
read-number ........................................... 195 , 196, 335
Reference Manual ....................................................xv
refresh ..................................................................... 301
refresh-agenda ........................................................ 305
release-mem ........................................................... 322
remove .................................................................... 193
remove-break.......................................................... 301
rename .................................................................... 193
replace$ .......................................................... 174 , 175
replace-member$ .................................................... 177
reset ..10, 12, 13, 22, 70, 125, 127, 155, 163, 284, 307
rest$ ........................................................................ 176
restore-instances ..................................................... 321
RETE algorithm ..................................................... 346
retract..........................................................10, 49, 231
return ..........26, 87, 143, 155, 212, 213, 214 , 243, 279
rewind ............................................................. 198 , 333
RHS .......................................................................... 24
right-hand side .......................................................... 14
round .............................................................. 208 , 335
roundoff ...................................................................... 5
rule...................................................................... 14 , 24
run ..................................................................155, 303
salience .......................................................26, 67 , 305
dynamic ...............................................26, 67 , 305
save ................................................................. 283 , 323
save-facts ........................................................ 294 , 335
save-instances ......................................... 319 , 320, 335
seed ...................................................................30, 219
seek ................................................................. 198 , 333
semicolon ...............................................................6, 9
send ....................15, 17, 110, 121, 124, 125 , 317, 348
sequence expansion .................................................. 36
sequencep ............................................................... 336
set-auto-float-dividend ........................................... 336
set-break ................................................................. 300

```
set-class-defaults-mode ......................................... 266
set-current-module................................. 150, 276 , 303
set-dynamic-constraint-checking.... 20, 109, 156, 283,
286
set-error ......................................................... 223 , 334
set-fact-duplication .......................................... 10, 295
setgen ..................................................................... 218
set-incremental-reset ............................................. 336
set-locale ........................................................ 195, 196
set-profile-percent-threshold ................................. 328
set-reset-globals ............................................... 70, 307
set-salience-evaluation .............................. 26, 67, 304
set-sequence-operator-recognition ........................ 280
set-static-constraint-checking ................................ 336
set-strategy............................................... 26, 163, 304
show-breaks ........................................................... 301
show-defglobals..................................................... 306
significant digits ........................................................ 5
single-field value ....................................................... 7
single-field wildcard ................................................ 33
slot ....... 11 , 12, 13, 17, 94, 95, 98 , 104, 125, 258, 312
access...................................... 102, 108, 258, 259
accessor .................................................. 107 , 141
put-<slot-name> ...................................... 126
default value ............. 99, 101, 126, 128, 270, 319
direct access ........................... 114 , 129, 141, 209
existence ......................................................... 258
facet .......................................................... 99, 104
inheritance propagation .................................. 104
overlay ............................................................ 104
override .......................................................... 103
visibility.......................................................... 259
slot daemons .......................................................... 348
slot-allowed-classes ............................................... 267
slot-allowed-values ................................................ 265
slot-cardinality ....................................................... 264
slot-default-value ................................................... 266
slot-delete$ ............................................................ 275
slot-direct-accessp ................................................. 259
slot-direct-delete$ .................................................. 275
slot-direct-replace$ ................................................ 274
slot-existp .............................................................. 258
slot-facets............................................................... 262
```

```
CLIPS Basic Programming Guide 411
```

slot-initablep ........................................................... 259
slot-insert$ ........................................................99, 275
slot-override ...........................125, 126, 128, 270, 319
slot-publicp ............................................................. 259
slot-range ................................................................ 265
slot-replace$ ........................................................... 274
slot-sources ............................................................. 263
slot-types ................................................................ 263
slot-writablep.......................................................... 258
Smalltalk ............................................................79, 92
sort .......................................................................... 220
space ........................................................................... 6
specificity ................................................................. 27
sqrt .......................................................................... 206
standard math functions ......................................... 199
str-cat ...................................................................... 179
str-compare ............................................................. 182
str-explode .............................................................. 336
str-implode ............................................................. 336
str-index.......................................................... 180 , 335
string ...................................................................5, 6 , 7
stringp ..................................................................... 164
string-to-field.................................................. 184 , 335
str-length ................................................................ 183
str-replace ....................................................... 184 , 333
subclass .................................... 95 , 121, 258, 312, 315
subclassp ................................................................ 258
subseq$ ................................................................... 174
subset ...................................................................... 336
subsetp .................................................................... 172
sub-string ................................................................ 179
superclass .............................94, 95 , 98, 111, 258, 312
direct ................................................................. 95
superclassp ............................................................. 258
switch .......................................................87, 215 , 279
symbol ........................................................5, 6 , 7, 272
reserved ............................................................. 10
and.............................................................. 11
declare ........................................................ 11
exists .......................................................... 11
forall ........................................................... 11
logical ........................................................ 11

```
not ............................................................. 11
object ......................................................... 11
or ............................................................... 11
test ............................................................. 11
symbolp ................................................................. 164
symbol-to-instance-name ...................................... 272
sym-cat .................................................................. 179
system .................................................................... 286
system .................................................................... 335
tab ...................................................................... 6, 188
tell .................................................................. 198 , 333
template ................................................................. 232
then portion.............................................................. 14
tilde ............................................................................ 6
time ........................................................................ 220
timer....................................................................... 221
timetag ................................................................... 336
toss ......................................................................... 327
trigonometric math functions ................................ 203
truth maintenance .................................................... 60
type function .................................................. 253 , 271
unconditional support .............................................. 61
undefclass .............................................................. 312
undeffacts .............................................................. 297
undeffunction......................................................... 308
undefgeneric .......................................................... 309
undefglobal ...................................................... 70, 306
undefinstances ....................................................... 318
undefmessage-handler ........................................... 316
undefmethod .......................................................... 310
undefrule ........................................................ 150, 298
undeftemplate ........................................................ 291
unget-char ...................................................... 195 , 333
union$ .................................................... 177 , 178 , 336
unmake-instance .............................................. 49, 270
unwatch ................................................................. 290
upcase .................................................................... 181
User’s Guide ............................................................ xv
user-functions ........................................................ 329
value .......................................................................... 7
variable .............................. 6, 8 , 10, 13, 31, 32, 36, 54
global ................................ 2, 13, 67, 70 , 209, 284
```

```
412 Index
```

vertical bar .................................................................. 6
visible ..................................................................... 293
void ......................................................................... 334
vtab ......................................................................... 188
watch ..........................................26, 70, 288 , 290, 336
watch item
activations .................................................26, 289
all..................................................................... 289
compilations ............................................282, 288
deffunctions..................................................... 289
facts .................................................230, 231, 288
focus ................................................................ 289

```
generic-functions ............................................ 289
globals ...................................................... 70, 289
instances ......................................................... 289
message-handlers ........................................... 289
messages ......................................................... 289
methods .......................................................... 289
rules ........................................................ 289 , 303
slots ................................................................ 289
statistics .......................................................... 289
while ........................................................ 87, 212 , 279
wildcard ....................................................... 31, 32, 33
wordp ..................................................................... 336
```
