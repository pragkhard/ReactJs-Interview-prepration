Client side Rendering vs Server Side Rendering
------------------------------------------------

* Server is the part of our backend and client is more of what we see in front of it.
* Client side rendering means an app which is compeletely being rendered on the browser.
* React allows us to create client rendered appliction.
* We can take the example of fetching the data from the API's
* But what is client render means - right click and go to the view page source. All the data coming from API display on the browser but we can not see in the view page source / in the HTML document. We just have the div ID root.
* All the data rendered in the element tab is not useful for us because Google is not able to crawl this data and hence website won't be ranked on Google search results because you know if lets see if we are showcasing iPhone9 or lets say Samsung universe 9 device in our website. If someone searches this on Google, they won't be able to find that product exists on our website because Google search engines can not crawl it . This is an example of a client rendered application.

Client side Rendering Props & Cons-
------------------------------------
Props - 
* Rich interaction - 
In client side rendering we have the rich interaction. we are using something like react-router, whenever we click on any other link so yu can see the website chnages instantly. Client rendered app give us the feeling of you know basically a nativeness to that app. 
like for example when we use an app inside of our mobile phone everthing is just instant.

* Reduced server load -
Most of the rendering done on the client side, it reduces the load on the server. 
If we go to the network and just see the JS file that we're getting inside it we can see the chunk og javascript coming from backend. so that a huge js file whch is resposible for injecting the code inside of this dev with ID root . So most of the rendering is happening in the frontend which result in reduced server load.

* Better client-side caching -
If we have any assets lets say images , if we sent any websites and has a bunch of images, first time it will takes a lot of time but when you refresh the page next time the image load instantly. That's why it is better for client side caching. But evertime if its coming from the server, we have , to load those images again and again.

Cons-
* Server initial load - Since we have huge chunk of JS data from backend. Imagine we have bigger react application lets say ecommerce site. what's gonna happen there, our website take quite a lot of while to load and yeah we wil discuss a lot of otimization techniques as we move forward. Ecommerce web server or something like that. If you're completely making it client rendered, then definitely it will be slower in initial load.

* Bad for SEO - Since we don't get anything inside of our page source, we're just getting an empty HTML. So, its not at all good for SEO
* Dependency on the user's device - There is a dependency on the user's device because every single function is happening. Every single functionality, is taking place on the user's device and it's dependent on the browser's capability.

So the solution for this server side rendering.

Server Side Rendering-
-------------------------
When coem
Props -
* Faster initial page load
* Better SEO
* Consistent performance

Cons -
* Increased lod of server
* Frequent server requests can increase latency
* More complex to implement 

Use cases- 
------------
Client-Side - Ideal for application that require rich interations after initial load. such as single-page application where SEO is not a primary concern.

Server-Side - Best for content-heavy sites where SEO and fast initial load times are crucial, such as ecommerce sites and news websites.



