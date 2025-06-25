React profiler
---------------

React profiler it bascially a part of react developer tool/ react devps tool

How do you install it - 

https://react.dev/learn/react-developer-tools

https://chromewebstore.google.com/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en

----------------------------------------------------------------------------------------------------------

What basically does is - 
---------------------------
Inspect - > We get these two extra options overe there -> Components and profiler
![alt text](image.png)

We need to understand why do we need this component & profiler ?
we already have elements tab which shows all the dives and everthing. This is with respect to like transpiled data. This is converted data/JSX into normal HTML. If you want to see the JSX we can not see over there

Component -
------------

* If we go to the component section you're going to see it show us the exact level by level JSX of our app and all the tags that are included with all the details like its state and hooks, routing etc. It bascically provides us the complete information.

![alt text](image-1.png)

We have these icons over here - 

-------------------------------

1. 
![alt text](image-2.png)

First icon is Focus the selected component into an errored state. If i click on it you're gonna see our app which throws an error. Maybe this can be used for testing our erros like errow boundary.

2.
![alt text](image-3.png)

Second one is inspect the matching DOM element . Inspect the matching DOM element and If i want to see, where the element does exist inside the DOM. So, what i can do , I just click on the eye button and it will just take me directly to the div. 

3.
![alt text](image-4.png)

Log this component data to the console. If we want to see the further state, props. We can see there

![alt text](image-5.png)

4.
![alt text](image-6.png)

View source for this element. It will onto this source(src) tab and you can see where this is inside of our code.

![alt text](image-7.png)


Profiler -
-----------

Profiler is used for measuring the performance. It provide us the chat , this chart provides us how much time a particular component took to be rendered

If i click on this start profiling make the changes(ex. change the star rating)
![alt text](image-8.png)

It will provide the rank chart. This cart shows us how much time a particular component took to be rendered and we have the different different components a, different different times like - here we can see the render time in Rendered at section, here we can see home component re-renderd 2 times and star section takes 47.3 ms time

![alt text](image-10.png)

 And If i come over here in he flame grap chart, you can see the sequentially show us what are all things that got rendered or not rendered.

 ![alt text](image-11.png)

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

