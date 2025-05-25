Hooks-
======
* Functional component do not have state and life cycle method.
* To use state and lifecycle methods we can import hooks in functional component.

---------------------------------------------------------------------------------------------

useState – 
============
* useState is a hook for use state in functional.
* useState is a React Hook for managing component-level state / Local state of the component.
* React will automatically re-render the component when the state changes.
* 📌 useState changes cause re-renders.
* 📌 useEffect runs after render but does not trigger one. 🚀


* useState() is a React Hook that allows functional components to manage state. It takes an initial state value as an argument and returns an array with two elements: the current state value and a function to update it. When the state is updated using the provided function, the component re-renders to reflect the new state. 

* In this example, the useState() hook is used to declare a state variable count with an initial value of 0. The setCount function is used to update the count state variable. When the button is  clicked, the setCount function is called to increase the count, and the component re-renders with the updated state value.
---------------------------------------------------------------------------------------------

useEffect - useEffect is a React Hook used to handle side effects in functional components.
* ✅ It runs after the component renders.
* ✅ Used for API calls, event listeners, subscriptions, and DOM updates.
* ✅This is a hook for use lifecycle methods in the functional componet similar like a componentDidMount, componentDidUpdate, and componentWillUnmount

---------------------------------------------------------------------------------------------

Different Use Cases of useEffect -
==================================

Scenario & Behavior -

* No Dependency Array	-  Runs after every render (initial + on every state/prop update)
* Empty Dependency Array [] -	Runs only once after the first render (similar to componentDidMount)
* With Dependencies [btnNameReact] -	Runs after the first render and only when btnNameReact changes
