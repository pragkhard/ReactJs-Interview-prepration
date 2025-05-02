useRef-
========        
        
        import {useState, useEffect,useRef} from 'react'

        export default function App() {
            const inputRef =useRef(null)
        function handle(){
            inputRef.current.value = 1000;
        }
        return (<> 
            <input type="text" ref={inputRef}/>
            <button onClick={handle}>Click</button>
        </>)   
        }
