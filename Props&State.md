Difference between props and state- 
---------------------------------------
Both props and state are plain javascript object. Both of them hold information, they are different  in their functionality with respect to component. 

* Props are passing data from one component to another component where as in state data is not      accessible outside from component. 

* Props are Immutable cannot be changed directly within the component. State are  mutable can be changed using this.setState() in class components or state hooks in functional components. 

* In respect of data flow Props are Unidirectional passing data from parent to child components. State are Unidirectional changes trigger re-renders within the component. 