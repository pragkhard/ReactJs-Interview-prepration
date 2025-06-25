React profiler
---------------

React profiler it bascially a part of react developer tool/ react devps tool

How do you install it - 

https://react.dev/learn/react-developer-tools

https://chromewebstore.google.com/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en

----------------------------------------------------------------------------------------------------------

What is basically does is - 
---------------------------
Inspect - > We get these two extra options overe there -> Components and profiler

We need to understand why do we need this ?
We need this component & profiler
Works - Transpiled data (This is converted data/JSX into normal HTML)

Component -

If we go to the component section you're going to see it show us the exact level
and i want to see where does this exist inside of my DOM right in the element tab. So what can i do , i can just click on I button overe here and it will just take me directly to that div 

Profiler -
It provide us the chat , this chart provides us how much time a particular component took to be rendered 
And If i come over here in he flame grap chart, you can see the sequentially show us what are all things that got rendered or not rendered.

Grey - It says over here did not re-render 
Blue - data re-render

React developer tool is all about , this is how it helps us to you know, showcase our app, showcase the states and hooks that we're usig inside of our app, potentially improve the performanace of our apps.

-------------------------------------------------------------------------------------------------------

There are multiple techniques in React that we can use to optimize our application, and one of the most useful tools for this is the React Profiler, which is part of the React Developer Tools extension.

Once we install the React Developer Tools, we get two additional tabs in the browser dev tools: Components and Profiler.

The Components tab helps us visualize the complete component hierarchy of the application. It transpiles JSX into regular HTML and lets us inspect props, state, and hooks. This makes debugging much easier by allowing us to trace where each component exists and how it behaves in the DOM.

The Profiler tab provides a performance chart that shows how much time each component took to render or re-render. This visual representation helps us identify performance bottlenecks and optimize components accordingly.

Together, these tools help us inspect, debug, and optimize our React application more effectively.

--------------------------------------------------------------------------------------------------------

There are multiple techniques in react using that we can optimized our react application . we do have react profile, It is basically the part of react dev tools so after installing the react dev tool and the extension it will provide us the component and profiler tab. It basically transpiled jsx into HTML . by using the component we can see the hierarchy tree of the complete app so using it easily we can debug and profiler is basically provide us the chart of the render and re-render so using it we can optimize the component 