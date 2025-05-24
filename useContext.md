useContext
1.	Create Context using createContext
2.	Provide Context in Parent
3.	Consume Context in Child using useContext hook in the child component.


App.js
=======

        import React, { createContext, useState } from "react";
        import Child from "./Child";

        // Create Context
        export const MyContext = createContext();

        export default function App() {
        const [value, setValue] = useState("Hello from Context!");

        return (
            <MyContext.Provider value={{ value, setValue }}>
            <div>
                <h1>Parent Component</h1>
                <Child />
            </div>
            </MyContext.Provider>
        );
        }


Child.js
=========

        import React, { useContext } from "react";
        import { MyContext } from "./App";

        export default function Child() {
        const { value, setValue } = useContext(MyContext);

        return (
            <div>
            <h2>Child Component</h2>
            <p>Value from Context: {value}</p>
            <button onClick={() => setValue("Updated from Child!")}>
                Update Value
            </button>
            </div>
        );
        }
