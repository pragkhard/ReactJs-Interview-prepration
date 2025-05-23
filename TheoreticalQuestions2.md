Virtual DOM
------------
The Virtual DOM is a lightweight, in-memory representation of the actual DOM. When there are changes in a React component React first updates the Virtual DOM instead of the real DOM directly, it calculate the difference between updated Virtual DOM with the previous version(this process is called "diffing"). Once the calculations are done,then the real DOM will be updated with only the things that have actually changed. The entire process called reconciliation. 

This process improve the performance by reducing unnecessary re-renders and DOM manipulations and enhancing the application's speed and efficiency.

In-memory representation refers to how React converts UI components into JavaScript objects.

--------------------------------------------------------------------------------------------------------

React is widely used nowadays instead of Angular or Vue. What are the main features or benefits of React that make developers prefer it?
--------------------------------
According to my understanding- 

React, is an open-source JavaScript library.It is used for building single-page applications It means application looks like a single page and not reload and refresh on jumping on the other page and links. It focuses on component-based development, utilizes a virtual DOM so when there are changes in a React component React first updates the Virtual DOM instead of the real DOM directly, it calculate the difference between updated Virtual DOM with the previous version. Once the calculations are done,then the real DOM will be updated with only the things that have actually changed. The entire process called reconciliation. This process improve the performance by reducing unnecessary re-renders and DOM manipulations and enhancing the application's speed and efficiency,
allows JSX, enforces unidirectional data flow makes debugging of the application more easier

Unlike other JavaScript frameworks such as Angular or Vue follow the MVC architecture, React focuses on the (V) view layer only.This gives developers more flexibility to integrate and choose their preferred tools or libraries — such as React Router for routing or Redux for state management — based on the project’s needs.

 It also supports mobile app development through React Native and benefits from an active and supportive community. 

--------------------------------------------------------------------------------------------------------
JSX
-----
JSX (JavaScript XML) in React.js is a syntax extension that allows developers to write HTML-like code directly in JavaScript files.  
JSX makes React code more readable and intuitive. 
During compilation, JSX is transformed into JavaScript code, enabling the creation of React elements for rendering on web pages/ enabling React to render components efficiently.

--------------------------------------------------------------------------------------------------------

What is the significance of keys in React?
---------------------------------------------

In React, keys are used to uniquely identify elements, especially when rendering lists. Every component or element in a list should have a unique key to help React efficiently update and re-render components when the data changes.

For example, instead of hardcoding multiple list items, we usually use the map() function to dynamically render components from an array. In such cases, assigning a unique key to each item helps React track which items have changed, been added, or removed.

We should avoid using array indexes as keys because when items are added, removed, or reordered, the indexes can change, leading to performance issues and unexpected behavior during re-renders.

--------------------------------------------------------------------------------------------------------

Unique Key id while using map-
--------------------------------

*   Each item in the list must be uniquely identified
    DOM is going to re-render all the components again. As DOM can’t identify where to place it. But if we give each of them a unique ID then react knows where to put that component according to the ID. It is a good optimization and performance thing. Note* Never use index as keys in map. It is not recommended.

*   named exports, you have to write curly braces and then whatever you need to import.
*   If we use default export, then no need to use curly bracket at the time of import.

----------------------------------------------------------------------------------------------------------

What are Synthetic Events in React?
---------------------------------------------

In React, Synthetic Events are wrapper objects around the browser’s native events. They provide a consistent and cross-browser interface to handle events in a React application.

Instead of directly using the native DOM events, React uses its own event system called the Synthetic Event system. For example, when you use onClick, onChange, or onSubmit in React, you’re actually using synthetic events.

These events work the same way across all browsers, and React handles the event delegation internally for better performance and compatibility.

----------------------------------------------------------------------------------------------------------

What do you understand by references in React?
-----------------------------------------------
We are using use ref hook for creating refs
what refs does the ref will contain all the component code over there so we can manipulate that particular components uh events and contents by using refs