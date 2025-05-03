Redux
=======
* Purpose: Redux is a state management library used for managing and centralizing application state.
* Architecture: It sits at the top level of your application and maintains a single source of truth (a single store).
* State Access: Any component in the React app can access the state by:
     * Dispatching actions
     * Using reducers to update state
     * Selecting a slice of state from the store
* Case: Ideal for large-scale applications where multiple components need to share and update state consistently.

Context API
==========
* Purpose: Context API is a built-in feature in React used for prop drilling avoidance and simple state sharing.
* Structure: It consists of two main parts:
    * Provider: Supplies the data at a higher level in the component tree.
    * Consumer: Any nested component can consume the data provided.
* State Access: Components wrapped in the consumer can access the data directly without passing props manually.
* Use Case: Commonly used for authentication, theme settings, or user preferences—scenarios where state is not frequently updated or deeply nested.