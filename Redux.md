explain the redux in interview, frame the sentenses- 
When I click on the add button how does the data go inside the card slice
We cannot directly add data to the card slice , redux say that you can directly modify the card slice
There is a way we can do that –
Suppose I click on this add button It will dispatch an action, what will happen after dispatching an action , it calls a
function and the function(reducer) internally modifies the card.
Now what is the function actually – This function known as the reducer
Once again when I click on the add button it dispatches an action which calls the reducer function which
modifies /updates the slice of redux store. Now the card slice has some data inside of it. This is how to write the
data


 ----------------------------------------------------------------------------------------------------------

Suppose I want to read data. Now I want to get this data to some other part. How can I read data
For that we use selector to read the data from our store and the selector will modify are react component . This is
how we read data. Selector will give you data over here.
When we use selector, this phenomenon known as subscribing to the store
We say that header component subscribe to a store and when I say subscribe the store basically we shink with the
store. If the data inside the store changes my header component will update automatically.
How do you subscribe – will subscribe using the selector


* The Redux Toolkit package is intended to be the standard way to write Redux logic.