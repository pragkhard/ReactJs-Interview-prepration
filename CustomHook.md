CustomHook-
-----------
You need to fetch data from an API in multiple components. Without a custom hook, you'll have to duplicate the useEffect and fetch logic in every component.


Create "useFetch.js" custom hook – 
==================================

        import { useState, useEffect } from "react";

        export function useFetch(url) {
        const [data, setData] = useState([]);

        const fetchData = async () => {
            const response = await fetch(url);
            const result = await response.json();
            setData(result);
        };
        useEffect(() => {
            fetchData();
        }, [url]);

        return data;
        }


Import the  custom hook in App.js -
-----------------------------------

        import { useFetch } from "./useFetch"; // Import the custom hook
        export default function App() {
        const data = useFetch("https://jsonplaceholder.typicode.com/posts"); // Use the hook
        return (
            <>
            <h1>Hello </h1>
            <ul>
                {data.map((item) => (
                <li key={item.id}>{item.title}</li>
                ))}
            </ul>
            </>
        );
        }



