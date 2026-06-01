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
   
        And
   
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

* useEffect with an Empty Dependency Array [] & wihout Dependency Array
# With an Empty Dependency Array [] -
  
          useEffect(() => {
          fetchUsers();
        }, []);

- The effect runs only once after the component is rendered for the first time (component mount).
- fetchUsers() is called once.
- API is hit only once.
- When setUsers(data) updates the state, the component re-renders, but the effect does not run again because the dependency array is empty.

 # Without an Empty Dependency Array [] -
 
          useEffect(() => {
                  fetchUsers();
                }, []);

- The effect runs after every render.
- fetchUsers() calls the API.
- setUsers(data) updates state.
- State update causes a re-render.
- After re-render, useEffect runs again.
- API is called again.               
                
Flow - 
        Initial Render
              ↓
        users = []
              ↓
        UI shows nothing
              ↓
        useEffect runs
              ↓
        fetchUsers()
              ↓
        API returns data
              ↓
        setUsers(data)
              ↓
        State changes
              ↓
        Re-render
              ↓
        users contains data
              ↓
        UI shows user names
              ↓
        useEffect skipped because []

with-
Initial render means the first time React executes the component and paints the UI on the screen. In this example, users is initially an empty array, so nothing is displayed. After the component mounts, useEffect runs once because the dependency array is empty. It fetches data from the API and updates the state using setUsers. The state update triggers a re-render, and now the user list is displayed. Since the dependency array is empty, the effect does not run again after the re-render.  

without-
Initial render means the first time React executes the component and paints the UI on the screen. In this example, users is initially an empty array, so nothing is displayed. After the component mounts, useEffect runs because no dependency array is provided. It fetches data from the API and updates the state using setUsers. The state update triggers a re-render, and now the user list is displayed. However, because there is no dependency array, useEffect runs again after every re-render. It fetches the data again and calls setUsers, which updates the state and causes another re-render. This process keeps repeating, resulting in continuous API calls and an infinite render loop.
        
        

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

