EY - 19/may/2025
1. difference between usestate, useReducer and usecontext/ Explain usecontext
------------------------------------------------------------------------------------------
* useState: A hook to manage local state in functional components.
* useReducer: An alternative to useState for complex state logic with multiple actions.
* useContext: A hook to access global state or values without prop drilling.

------------------------------------------------------------------------------------------
2. How do you maintain code quality in your React project
------------------------------------------------------------------------------------------

To maintain code quality in my React project, we follow a mix of best practices, team standards, and automated tools. First, we follow consistent code style using ESLint and Prettier, which help catch syntax errors and enforce formatting rules before code is committed."

"We use TypeScript or PropTypes to add type safety, which helps avoid runtime errors. For state management, we keep the logic clean and centralized using Context API or Redux Toolkit."

"Before pushing code, we write unit and integration tests using Jest and React Testing Library to make sure components behave as expected. We also conduct regular peer code reviews via pull requests, where we discuss improvements, reusability, and performance."

"Additionally, we use tools like SonarQube or code coverage reports in CI pipelines to detect code smells and ensure test coverage goals are met. These practices help us keep the codebase clean, scalable, and easy to maintain."

We maintain code quality by combining coding standards, reusable patterns, and automation.

First, we enforce consistent syntax and best practices using ESLint and Prettier.

Our project follows a modular folder structure and uses reusable components to reduce duplication.

For state management, we use React hooks or Redux Toolkit, keeping logic separate from the UI to make components easier to test and maintain.

Every code change goes through a pull request with peer reviews, which helps us catch issues early and share knowledge within the team.

We write unit and integration tests using Jest and React Testing Library to ensure components behave as expected.

Finally, we use CI pipelines that automatically run tests and lint checks before any deployment.

These steps together help us write clean, stable, and maintainable code across the project."

------------------------------------------------------------------------------------------
3. What is Generic means?
------------------------------------------------------------------------------------------
Generic means building reusable components or logic that can be used in multiple places, making the codebase cleaner, scalable, and easier to maintain.

------------------------------------------------------------------------------------------
4. Can you briefly describe the generic or reusable features you implemented in your banking and finance project?
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
5. How do you implement a generic or reusable button component in React?
OR Can you explain how you implemented a reusable button component in your React project that supports different variants, sizes, and behaviors?
 ----------------------------------------------------------------------------------------------------------
"To implement a generic button component in React, I create a reusable <Button /> component that accepts common props like type, variant, size, disabled, and onClick. This allows the same button to be used in different contexts like forms, modals, or toolbars."

"I use conditional class names (with Tailwind CSS or classnames library) to support different styles like primary, secondary, outline, or danger. I also allow for left or right icons, a loading spinner, and a className prop for extra customization."

"This way, developers don’t need to rewrite styles or logic—they just pass the props they need. It ensures consistency across the app, improves maintainability, and speeds up development."

Button.js

        import React from "react";
        import classNames from "classnames";

        const Button = ({
        children,
        type = "button",
        variant = "primary",
        size = "md",
        disabled = false,
        onClick,
        className = "",
        }) => {
        const baseStyles = "rounded font-medium focus:outline-none transition";
        
        const variantStyles = {
            primary: "bg-blue-600 text-white hover:bg-blue-700",
            secondary: "bg-gray-200 text-black hover:bg-gray-300",
            outline: "border border-blue-600 text-blue-600 hover:bg-blue-50",
        };

        const sizeStyles = {
            sm: "px-3 py-1 text-sm",
            md: "px-4 py-2",
            lg: "px-5 py-3 text-lg",
        };

        const buttonClass = classNames(
            baseStyles,
            variantStyles[variant],
            sizeStyles[size],
            className,
            { "opacity-50 cursor-not-allowed": disabled }
        );

        return (
            <button type={type} className={buttonClass} onClick={onClick} disabled={disabled}>
            {children}
            </button>
        );
        };

        export default Button;

App.js

        import Button from "./Button";

        function App() {
        return (
            <div className="p-4 space-x-4">
            <Button variant="primary">Submit</Button>
            <Button variant="secondary" size="sm">Cancel</Button>
            <Button variant="outline" size="lg" disabled>Disabled</Button>
            </div>
        );
        }

6. React Project Architecture-
----------------------------

7. Performance Optimisation approaches
----------------------------------------

8. lazy loading
-----------------


