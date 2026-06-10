AbortController is used to cancel an ongoing API request. 
Sometimes an API takes too long to respond, or the user navigates to another page before the response arrives.
In such cases, we don't need the API response anymore, so we abort the request to save network resources, improve performance, 
and avoid unnecessary state updates.
