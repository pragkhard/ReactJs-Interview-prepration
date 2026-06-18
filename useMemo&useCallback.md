useMemo vs. useCallback 
---------------------------
* ✅ useMemo → Memoizes a value (avoids re-calculation)
* ✅ useCallback → Memoizes a function (avoids re-creation)

useMemo
=========

        import { useMemo, useState } from "react";

        export default function App() {
        const [text, setText] = useState("");
        const [count, setCount] = useState(0);

        // Without using useMemo
        // const squared = count * count;
        // console.log("Calculating squared...");

        // With using useMemo
        const squared = useMemo(() => {
            console.log("Calculating squared...");
            return count * count;
        }, [count]);

        return (
            <>
            <p>{squared}</p>
            <input type="text" onChange={(e) => setText(e.target.value)} />
            <button onClick={() => setCount(count + 1)}>On Click</button>
            </>
        );
        }

Another example -

        import {useState, useMemo} from 'react';
        export default function App() {
          const[data, setData] = useState(0)
        
           // const square = data*data;
           //  console.log("re-rendering") 
          
            const square = useMemo(()=>{
              return data*data;
            console.log("re-rendering") 
            },[data])
            
          return (
            <>
              <h1>{square}</h1>
              <button onClick={()=>setData(data + 1) }>On Click</button>
            </>
          )
        }

useCallback
============

        import { useState } from "react";
        export default function App() {
        const [count, setCount] = useState(0);
        const [text, setText] = useState("");

        // Function is recreated on every render
        // Without using useCallback
        const handleClick = () => {
            console.log("Button clicked!");
        };
        console.log("Component re-rendered!");

        // Without using useCallback
          const handleClick = useCallback(() => {
            console.log("Button clicked!");
        }, []);

        return (
            <div>
            <h2>Count: {count}</h2>
            <button onClick={() => setCount(count + 1)}>Increment</button>
            <input onChange={(e) => setText(e.target.value)} placeholder="Type something" />
            <button onClick={handleClick}>Click Me</button>
            </div>
        );
        }
      




