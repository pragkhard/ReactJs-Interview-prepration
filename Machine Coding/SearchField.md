                import React, { useState } from "react";

                export default function App() {
                const fruits = ["Apple", "Banana", "Mango", "Watermelon", "Jackfruit", "Pear"];

                const [search, setSearch] = useState("");
                const [list, setList] = useState([]);

                const filteredFruits =
                    search &&
                    fruits.filter((fruit) =>
                    fruit.toLowerCase().includes(search.toLowerCase())
                    );

                return (
                    <div>
                    <input
                        type="text"
                        placeholder="Search fruit"
                        value={search}
                        onChange={(e) => setSearch(e.target.value)}
                    />

                    {search && (
                        <ul>
                        {filteredFruits.map((fruit, i) => (
                            <li
                            key={i}
                            onClick={() => {
                                setList([...list, fruit]);
                                setSearch("");
                            }}
                            >
                            {fruit}
                            </li>
                        ))}
                        </ul>
                    )}

                    <h3>Saved List</h3>

                    <ul>
                        {list.map((item, i) => (
                        <li key={i}>{item}</li>
                        ))}
                    </ul>
                    </div>
                );
                }
