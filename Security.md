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
