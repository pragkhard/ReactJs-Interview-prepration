Fetch the data from API - 
==========================

Using fetch method-
====================

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

NOTE:
* async should be in small letter
*  Difference between two 
        <div>
              {users.map((user) => (
                <p key={user.id}>{user.name}</p>
              ))}
            </div>
        and 
        -- (Does Not Work)-- 
        <div>
              {users.map((user) => {
        
                <p key={user.id}>{user.name}</p>
        
              })}
        </div>
        
        -- (Works)-- 
        <div>
              {users.map((user) => {
                return <p key={user.id}>{user.name}</p>
        
              })}
        </div>

When an arrow function always use parentheses (), the value is returned automatically (implicit return). 
When it uses curly braces {},which create a function body and you must explicitly use the return keyword. 
Without return, the function returns undefined, so React won't render anything.


Using Axios -
==============

        import React, { useEffect, useState } from 'react';
        import axios from 'axios';

        const DummyData = () => {
        const [users, setUsers] = useState([]);

        useEffect(() => {
            // Fetch data when the component mounts
            axios.get('https://jsonplaceholder.typicode.com/users')
            .then(response => {
                setUsers(response.data); // Store the data in state
            })
            .catch(error => {
                console.error('Error fetching data:', error);
            });
        }, []);

        return (
            <div>
            <h2>Dummy Users</h2>
            <ul>
                {users.map(user => (
                <li key={user.id}>
                    {user.name} ({user.email})
                </li>
                ))}
            </ul>
            </div>
        );
        };

        export default DummyData;

