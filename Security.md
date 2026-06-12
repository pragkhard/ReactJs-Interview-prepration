How do you ensure API security?
------------------------------------

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

3. After successful authentication, the server creates a session and generates a unique Session ID.
   The process does not stop after authentication here After the user logs in successfully, the server knows who the user       is. However, when the user makes the next request, the server does not automatically remember the previous login because     HTTP is stateless.To remember the user, the server creates a Session ID and sends it to the browser in a cookie.
   From then on, the browser automatically sends that Session ID with every request. When the server receives the SessionID,    it recognizes the user and knows they have already logged in. This way, the user does not have to enter their username       and password again on every page.
   The server creates a Session ID after authentication so it can remember the user across multiple requests and avoid          asking them to log in again every time.  
   
   
   
   
