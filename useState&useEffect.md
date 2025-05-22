Hooks-
======
* Functional component do not have state and life cycle method.
* To use state and lifecycle methods we can import hooks in functional component.

---------------------------------------------------------------------------------------------

useState – 
============
useState is a React Hook for managing component-level state.
React will automatically re-render the component when the state changes.
* 📌 useState changes cause re-renders.
* 📌 useEffect runs after render but does not trigger one. 🚀

---------------------------------------------------------------------------------------------

useEffect - useEffect is a React Hook used to handle side effects in functional components.
* ✅ It runs after the component renders.
* ✅ Used for API calls, event listeners, subscriptions, and DOM updates.

---------------------------------------------------------------------------------------------

Different Use Cases of useEffect -
==================================

Scenario & Behavior -

* No Dependency Array	-  Runs after every render (initial + on every state/prop update)
* Empty Dependency Array [] -	Runs only once after the first render (similar to componentDidMount)
* With Dependencies [btnNameReact] -	Runs after the first render and only when btnNameReact changes
