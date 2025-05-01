Fetch the data from API - 
      
        import { useState, useEffect } from "react";
        export default function App() {
        const [data, setData] = useState([]);
        const fetchData = async () => {
            const respose = await fetch("https://jsonplaceholder.typicode.com/posts");
            const result = await respose.json();
            setData(result);
        };
        useEffect(() => {
            fetchData();
        });
        return (
            <>
            <h1>Hello</h1>
            {data.map((item) => (
                <li>{item.title}</li>
            ))}
            </>
        );
        }
