What is State?
---------------
* Information Holder inside component and it store any data like a variable. 

* When we update state component will re-render again but not in case of variable.

* We can not use state outside to component.

* State of a component is a object that hold some information that may change over the life-cycle of the component. It is like a props but It is used for internal communication inside a component and it is not accessible outside of the component. When we update state component will re-render again but not in case of variable.

* In class components It is initialized and managed using the this.state object.

* In functional components state can be declared and managed by using useState hook.
----------------------------------------------------------------------------------------------------------

What is Props?
----------------
* Share data between component.
* We can send data parents to child, child to parent, and in sibling component.
* We can not change props in receiving component.

----------------------------------------------------------------------------------------------------------

Difference between props and state- 
---------------------------------------
Both props and state are plain javascript object. Both of them hold information, they are different  in their functionality with respect to component. 

* Props are passing data from one component to another component where as in state data is not      accessible outside from component. 

* Props are Immutable cannot be changed directly within the component. State are  mutable can be changed using this.setState() in class components or state hooks in functional components. 

* In respect of data flow Props are Unidirectional passing data from parent to child components. State are Unidirectional changes trigger re-renders within the component. 