            import React, { useState } from "react";
            const App = () => {
            const [inputValue, setInputValue] = useState("");
            const [tableData, setTableData] = useState([]);
            const handleInputChange = (e) => {
                setInputValue(e.target.value);
            };
            const handleAddToTable = () => {
                setTableData([...tableData, inputValue]);
                setInputValue("");
            };
            return (
                <div>
                <input type="text" value={inputValue} onChange={handleInputChange} />
                <button onClick={handleAddToTable}>Add to Table</button>
                <table>
                    <thead>
                    <tr>
                        <th>Data</th>
                    </tr>
                    </thead>
                    <tbody>
                    {tableData.map((data, index) => (
                        <tr key={index}>
                        <td>{data}</td>
                        </tr>
                    ))}
                    </tbody>
                </table>
                </div>
            );
            };
            export default App;
