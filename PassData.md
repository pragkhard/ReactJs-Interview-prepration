 Parent to Child-
===================
* Passing data from a Parent component down through a Child component to a GrandChild component using props across 3 levels

        // Parent.js
        function Parent() {
        const message = "Hello from Parent!";

        return <Child text={message} />;
        }

        // Child.js
        function Child({ text }) {
        return <GrandChild text={text} />;
        }

        // GrandChild.js
        function GrandChild({ text }) {
        return <div>{text}</div>;
        }

* Passing data from a Parent component down through multiple nested Child components (4 levels deep) using props:

        import React from "react";

        function Parent() {
        const message = "Hello from Parent!";

        return <Child1 text={message} />;
        }

        function Child1({ text }) {
        // Pass props down to Child2
        return <Child2 text={text} />;
        }

        function Child2({ text }) {
        // Pass props down to Child3
        return <Child3 text={text} />;
        }

        function Child3({ text }) {
        // Pass props down to Child4
        return <Child4 text={text} />;
        }

        function Child4({ text }) {
        // Finally use the prop
        return <div>{text}</div>;
        }

        export default Parent;


In React, data flow is unidirectional(one-way data flow), meaning it goes from parent to child through props — not the other way around. However, if we want a child component to update something in the parent, we can create state variables and functions in the parent component and then pass those functions down as props to the child component. In the child component, we use the props to call those functions, which then update the parent’s state. This is how we achieve indirect communication from child to parent.

Child-to-Parent-
================

Passing data from a child component to a parent can sometimes be tricky, but there are effective patterns to handle it.

* Recommended Approach: Using Callback Functions
* Define a callback function in the parent component.
* Pass this function as a prop to the child component.
* Invoke the callback in the child component whenever you want to send data back to the parent.

ParentComponent.jsx

        function ParentComponent() {
        const handleDataFromChild = (data) => {
            console.log("Received from child:", data);
        };

        return <ChildComponent onSendData={handleDataFromChild} />;
        }

ChildComponent.jsx

        function ChildComponent({ onSendData }) {
        return (
            <button onClick={() => onSendData("Hello from child!")}>
            Send Data to Parent
            </button>
        );
        }


⚠️ Alternative Approaches (Less Ideal)
* Refs or context can be used, but they often add unnecessary complexity.
* Lifting state up is usually a better solution when both parent and child need access to the same data.

💡 Best Practice
Always try to pass data from parent to child via props. If the child needs to update the parent, lift the state up to the parent and manage it there. This keeps your components clean and your data flow easy to trace.