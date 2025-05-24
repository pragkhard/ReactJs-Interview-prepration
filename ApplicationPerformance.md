How to make application performance-
--------------------------------------

so let's say if you are using a list of items if you are entering list of item on the screen
and if it's a use list then it's better to use infinite scrolling instead of displaying all the items in one go.

If you are using some image then get the image in low resolution in the form of thumbnail and then whenever user clicks it you get the actual image so that will make it performant and also we can use
lazy loading and functional components.

There are several performance optimization techniques in React and it totally depends on the use case -
prevents unnecessary re-renders of functional components the hook
useMemo → Memoizes a value (avoids re-calculating)
useCallback → Memoizes a function (avoids re-creating it)