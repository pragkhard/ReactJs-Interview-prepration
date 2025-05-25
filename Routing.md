 Basic Setup 
===============
 
1. Install React Router:
--------------------------

        npm install react-router-dom

2. Wrap with BrowserRouter in index.js/App.js:
------------------------------------------------

        import { BrowserRouter } from "react-router-dom";

        <BrowserRouter>
            <App />
        </BrowserRouter>

3. Define routes:
------------------

        <Routes>
            <Route path="/" element={<Home />} />
            <Route path="/about" element={<About />} />
        </Routes>

4. link
-------

        <nav>
           <Link to="/">Home</Link> 
           <Link to="/about">About</Link> 
        </nav>

5. useNavigate (Passing data from one page to another by using useNavigate)
-----------------------------------------------------------------------------

        const navigate = useNavigate();

        function goToAbout() {
        navigate("/about");
        }

        <button onClick={goToAbout}>Go to About</button>