1. difference between usestate, useReducer and usecontext 
--------------------------------------------------------
* useState: A hook to manage local state in functional components.
* useReducer: An alternative to useState for complex state logic with multiple actions.
* useContext: A hook to access global state or values without prop drilling.

------------------------------------------------------------------------------------------

2. What is Generic means?
------------------------
Generic means building reusable components or logic that can be used in multiple places, making the codebase cleaner, scalable, and easier to maintain.

3. Can you briefly describe the generic or reusable features you implemented in your banking and finance project?
------------------------------------------------------------------------------------------------
"In my current project for a banking client, I worked on the Payments and Debit Cards modules. One of the key real features I implemented was a reusable and secure fund transfer form."

🔧 Here’s how I made it generic and scalable:
🔁 Reusable Form Component:
"I built a dynamic form component using React, Formik, and Yup. It supported different transfer types (like NEFT, RTGS, IMPS) with dynamic validation rules based on transfer mode."

🔐 Secure API Layer:
"I integrated this with a generic Axios service that handled token-based authentication, error messages, and loading indicators across all modules."

🛡️ Role-Based Access Control:
"The fund transfer page had restricted access. I implemented role-based routing using React Router and Context API to ensure only certain user types could access high-value transfers."

📤 Generic Confirmation Modal:
"I also created a reusable confirmation modal that pops up before final submission — this modal is now used across multiple features like card blocking, address update, etc."

📊 Reusable Table Component:
"For transaction history, I created a generic table with pagination, sorting, and filtering. It was later reused in the Cards and Statements modules with different data inputs."

🔔 Toast Notifications:
"Success or failure messages after any API call were handled using a centralized toast utility using react-toastify — making alert handling consistent across the app."

----------------------------------------------------------------------------------------------------------

React Project Architecture-
----------------------------

