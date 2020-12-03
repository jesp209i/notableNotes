---
tags: [Distribueret, Store Systemer]
title: Reuse
created: '2020-11-20T11:56:08.520Z'
modified: '2020-12-03T08:04:57.777Z'
---

# Reuse
## Application domain vs solution domain objects
* Application objects, also called domain objects, represent concepts of the domain that are relevant to the system.
  - Identified by the application domain specialists and by the end users.
* Solution objects represent concepts that do not have a counterpart in the application domain
  - They are identified by the developers
  - Examples: Persistent data stores, user interface objects, middleware.

## Inheritance
* Implementation Inheritance
  - Also called class inheritance
  - Goal: Extend an applications' functionality by reusing functionality in parent class
  - Inherit from an existing class with some or all operations already implemented
* Specification Inheritance
  - Also called subtyping
  - Inherits from an abstract class with all operations specified, but not yet implemented

### Delegation vs implementation inheritance
Delegation is a way of making composition as powerfull for reuse as inheritance.  
In delegation two objects are involved in handling a request:
  - A recieving object delegates operations to its delegate
  - The developer can make sure that the receiving object does not allow the client to misuse the delegate object.  

Comparison
* Delegation
  - Pro
    - Flexibility: Any object canbe replaced at runtime by another one (as long as it has the same type)
  - Con
    - Inefficiency: Objects are encapsulated
* Inheritance
  - Pro
    - Straitforward to use
    - Supported by many programming languages
    - Easy to implement new functionality
  - Con
    - Inheritance exposes a subclass to the details of its parent class
    - Any change in the parent class implementation forces the subclass to change (which requires recomplilation of both)

## Patterns

| Design Pattern | Type | Anticipated Change | Phrase |
|---|---|---|---|
| Bridge | Structural | _New vendor, new technology, new implementation._  <br>This pattern decouples the interface of a class from its implementation.<br> It serves the same purpose as the Adapter pattern, except that the developer is not constrained by an existing component | - Must support future protocols |
| Adapter | Structural | _New vendor, new technology, new implementation,_ <br>This pattern excapsulates a piece of legacy code that was not designed to work with the system. <br>It also limits the impact of substituting the piece of legacy code for a different component. | - Must comply with existing interface<br>- Must reuse existing legacy component |
| Strategy | Behavioral | _New  vendor,  new  technology,  new  implementation._ <br>This pattern decouples an algorithm from its implementation(s). <br>It serves the same purpose as the Adapter and Bridge patterns, except that the encapsulated unit is a behavior. | - Policy and mechanisms should be decoupled<br>- Must allow different algorithms to be interchanged at runtime |
| Abstract Factory | Creational | _New vendor, new technology._  <br>Encapsulates the creation of families of related objects. <br>This shields the client from the creation process and prevents the use of objects from different (incompatible) families. | - Manufacturer independence<br>- Platform independence |
| Command | Behavioral | _New functionality._  <br>This patterns decouples the objects responsible for command processing from the commands themselves. <br>This pattern protects these objects from changes due to new functionality. | - All commands should be undoable<br>- All transactions should be logged |
| Composite | Structural |  _New complexity of application domain._  <br>This pattern encapsulates hierarchies by providing a common superclass for aggregate and leaf nodes. <br>New types of leaves can be added without modifying existing code. | - Must support aggregate structures<br>- Must allow for hierarchies of variable depth and width |


