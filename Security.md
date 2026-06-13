How do you ensure API security?
------------------------------------
API security is a combination of frontend and backend measures. As a React developer, I focus on securely consuming APIs and protecting user data.

* I use HTTPS to ensure data is encrypted during transmission.
* I implement authentication using JWT tokens or secure cookies.
* I send tokens in the Authorization header for authenticated requests.
* I avoid storing sensitive information such as API keys or secrets in the frontend code.
* I protect routes on the frontend, but I rely on the backend for actual authorization and role validation.
* I validate and sanitize user inputs to help prevent XSS attacks.
* I handle API errors securely and avoid exposing sensitive backend information to users.
* I use proper session management and token expiration handling to prevent unauthorized access.

------------------------------------------------------------------------------------------------------------------------
* Authentication checks whether the user is genuine or not by using the credentials such as username and password.
After successful login, the backend returns a JWT token.

* Authorization determines what an authenticated user can access based on roles and permissions.

Authentication comes first, followed by authorization.

* In simple words-
Authentication = Who are you?
Authorization = What can you do?

When people refer the AUTH that means that usually means both things together Authentication & Authorization

There is two type of Authentication
1. Session-Based Authentication
2. Token-Based Authentication (JWT)


Session-Based Authentication divided into 4 steps
---------------------------------------------------

<img width="1001" height="424" alt="image" src="https://github.com/user-attachments/assets/1f708093-647f-49cc-aad9-de5483aab2b1" />

1. When a user enters their email and password and clicks Login,
   the browser sends a POST request to the server containing the user's credentials.
   
2. Once the server receives the request, it verifies the user's identity.
   it checks whether the password that the user sent is the same as the password that has been stored.
   but we do not check the string password we check the hashed password using a library like brypt.
   basically brypt stored the hased version of the password in the database and when the user submitted the password it will    check those two password to make sure those two hashed password are the same password. If they match, the user's identity    is authenticated.

3. but it needs to let the client know that this request authenticated and for that it will set the cookies with the session ID that it just created and this is record to indicate that the user has been authenticated
how ever one problem is cookie is that anybody ready the cookie if it is not set correctly . The server set the cookie with an httpOnly flag which basically tells js it can not access this cookies and this cookie only be accessed once it will reaches the server and that to the server that set the cookies. This prevents malicious agents from authenticated session ID from the cookies

            res.cookie("session_id", sessionId,{
            httpOnly: true,
            maxAge: 1000*60*60*24*7
            })

4. This HTTP only flag is extremely important. Now the next time the user makes a request, we want to remember that the user logged in previously cuz
it would be terrible experience to make the user send their password over and over again. So for that we include this cookie that we had just set every time
we make a subsequent request. So in the future when we make a request we make sure to include the credentials using credentials include flag so that we are
including the session ID that we had just created and then the database checks the session ID on every request.

   Note: 
   The process does not stop after authentication in the 3rd step because After the user logs in successfully, the server       knows who the user is.However, when the user makes the next request, the server does not automatically remember the          previous login because HTTP is stateless.To remember the user, the server creates a Session ID and sends it to the           browser in a cookie.
   From then on, the browser automatically sends that Session ID with every request. When the server receives the SessionID,    it recognizes the user and knows they have already logged in. This way, the user does not have to enter their username       and password again on every page.
   The server creates a Session ID after authentication so it can remember the user across multiple requests and avoid          asking them to log in again every time.  
   
   
   
   
