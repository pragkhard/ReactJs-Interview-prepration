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