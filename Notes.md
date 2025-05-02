Create-react-app deprecate now , so either we can choose any of the framework like nextjs or use any of the bundlers like vite or parcle we can install react locally.
Vite is a frontend build tool that provides fast development and optimized production builds for web applications.
Vite is not Webpack, but Vite is an alternative to Webpack
https://vite.dev/
create the react project using vite-
1.	npm create vite@latest projectName
Select Framework, select variant 
2.	 cd react-vite-project
3.	  npm install [All the recommended packages install in the folder -install nodejs ]
4.	  npm run dev [Local:   http://localhost:5173/]

![alt text](image.png)


Difference between package.json & package-lock.json-
=======================================================

package.json-
----------------
Main purpose of package.json is to define project dependencies, name and version and it also contain scripts and metadata, It keeps the approx. version and it is editable by developers, editable minor version and major version. minor versions represent by * Caret sign (^) and major version is represent by Tilde sign (~)

package-lock.json-
---------------------
keeps the exact version of dependencies ensuring that whatever version is installed on my development machine is the same version used in the productions, locking the dependency version so that same version are used in both development and production, it is auto generated when we running npm installed should not be manually editable. 
"Imagine you’re working on a React project. You install react@18.2.0, and your teammate installs react@18.3.0 because of flexible versioning (^18.2.0). Now, your code works fine, but your teammate faces unexpected bugs due to breaking changes in the new version. This inconsistency can cause major issues in production."
✅ Solution: package.json defines the required dependencies, while package-lock.json ensures everyone installs the exact same versions, preventing version mismatches and unexpected bugs. 🚀

Npm and Npx- 
-------------
npm  - (Node Package Manager) installs packages globally or locally
npx - (Node Package eXecute) Runs packages without installing them globally

Normal Dependencies (dependencies) -Needed for the app to run in production
Dev Dependencies (devDependencies) - Only required for development/testing

Bundlers
----------
bundlers are tools used to combine multiple files (such as JavaScript, CSS, and images) from a project so that it can be shipped to production.
Examples: 1. Webpack 2. vite 3. Parcel

What is the dist Folder?
---------------------------
The dist (short for distribution) folder contains the compiled and optimized version of your application, that are ready for deployment.

JSX
-----
JSX (JavaScript XML) is a syntax extension for JavaScript that allows us to write HTML-like code inside JavaScript 
JSX makes React easier to read, write, and maintain while improving performance and preventing security risks.

Babel
-------
Babel is a JavaScript compiler that takes JSX and transforms it into plain JavaScript that browsers can understand. Since JavaScript engines only interpret ECMAScript (pure JavaScript), Babel ensures JSX and modern JavaScript features are converted for compatibility.

Why might code work locally but fail in production?
-------------------------------------------------------
several factors can cause failures in production due to differences in environment, dependencies, and configurations.

Optional chaining-
-----------------------
Optional chaining is a feature in JavaScript that allows you to safely access nested properties of an object or array, returning undefined instead of throwing an error if the property doesn't exist or is null/undefined.

Which components are better: class or functional?
----------------------------------------------------

Functional components are generally considered better than class components in modern React development. This is mainly because functional components allow you to write cleaner and more readable code, especially with the introduction of Hooks.

Hooks like useEffect let you handle side effects in a much simpler way. Instead of splitting logic across multiple lifecycle methods like componentDidMount, componentDidUpdate, and componentWillUnmount in class components, you can now combine all related logic into a single useEffect hook. This makes the code easier to manage and understand.

Additionally, functional components are lighter and more concise, which improves readability and performance. As a result, they have become the preferred choice in the React community.



