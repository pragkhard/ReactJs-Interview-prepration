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
![alt text](image.png)

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

There are multiple techniques in React that we can use to optimize our application, we do have react profile  which is part of the React Developer Tools extension.

Once we install the React Developer Tools, we get two additional tabs in the browser dev tools: Components and Profiler.

The Components tab allows us to see the component hierarchy tree of the entire application. It shows each component’s props, state, and hooks. This makes debugging much easier by allowing us to trace where each component exists and how it behaves in the DOM.

The Profiler tab provides a performance chart that shows how much time each component took to render or re-render. This visual representation helps us identify performance bottlenecks and optimize components accordingly.

Components in blue indicate they were re-rendered.
Components in grey indicate they did not re-render.

Together, these tools help us inspect, debug, and optimize our React application more effectively.

