Unique Key id while using map-
===================================
 
*   Each item in the list must be uniquely identified
    DOM is going to re-render all the components again. As DOM can’t identify where to place it. But if we give each of them a unique ID then react knows where to put that component according to the ID. It is a good optimization and performance thing. Note* Never use index as keys in map. It is not recommended.

*   named exports, you have to write curly braces and then whatever you need to import.
*   If we use default export, then no need to use curly bracket at the time of import.
