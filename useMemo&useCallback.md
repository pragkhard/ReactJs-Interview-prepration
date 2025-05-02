useMemo vs. useCallback 
---------------------------
✅ useMemo → Memoizes a value (avoids re-calculating)
✅ useCallback → Memoizes a function (avoids re-creating it)

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

useCallback
============



