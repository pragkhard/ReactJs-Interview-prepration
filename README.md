React
========
React, is an open-source JavaScript library .It is used for building single-page applications. It means application looks like a single page and not reload and refresh on jumping on the other page and links.  Its Developed and maintained by Facebook. 

Main feature of reactjs- 
-------------------------
React, is an open-source JavaScript library .It is used for building single-page applications. It focuses on component-based development, utilizes a virtual DOM for performance optimization, allows JSX , enforces unidirectional data flow, It also supports mobile app development through React Native and benefits from an active and supportive community. 
 
Virtual DOM- 
--------------
Virtual DOM is a lightweight copy of the actual DOM or we can say that it is an in-memory representation of real DOM. When there are changes in a React component, React first updates the Virtual DOM instead of the real DOM. Then, it compares the updated Virtual DOM with the previous version to calculate the difference between it. Once the calculations are done, the real DOM will be updated with only the things that have actually changed. The entire process called reconciliation This process improve the performance by reducing unnecessary re-renders and DOM manipulations and enhancing the application's speed and efficiency. 
 
Virtual DOM is an in-memory representation of real DOM. When there are changes in a React component the entire UI is re-rendered in Virtual DOM then it calculate the difference between the previous DOM representation and the new one. Once the calculations are done, the real DOM will be updated with only the things that have actually changed. The entire process called reconciliation.  

Difference between props and state- 
---------------------------------------
Both props and state are plain javascript object. Both of them hold information, they are different  in their functionality with respect to component. 

* Props are passing data from one component to another component where as in state data is not      accessible outside from component. 

* Props are Immutable cannot be changed directly within the component. State are  mutable can be changed using this.setState() in class components or state hooks in functional components. 

* In respect of data flow Props are Unidirectional passing data from parent to child components. State are Unidirectional changes trigger re-renders within the component. 

Unique Key id while using map-
--------------------------------

*   Each item in the list must be uniquely identified
    DOM is going to re-render all the components again. As DOM can’t identify where to place it. But if we give each of them a unique ID then react knows where to put that component according to the ID. It is a good optimization and performance thing. Note* Never use index as keys in map. It is not recommended.

*   named exports, you have to write curly braces and then whatever you need to import.
*   If we use default export, then no need to use curly bracket at the time of import.


