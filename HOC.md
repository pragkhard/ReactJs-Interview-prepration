Higher-Order Components (HOCs) are components used to modify or enhance existing components. For example, suppose we have a component that needs some special kind of data or requires common functionality shared by other components. Instead of repeating the same code, we create a higher-order function that contains this shared logic and data.

By using the higher-order component, we can wrap our other components to provide them with this common data or functionality. This way, we avoid duplication and keep our code clean and reusable.

So, you really need a Higher-Order Component in cases where multiple components require some common behavior or data.



        const withMessage = (WrappedComponent) => {
        return function Enhanced(props) {
            return <WrappedComponent {...props} message="Hello from HOC!" />;
        };
        };

        const MyComponent = ({ message }) => <h1>{message}</h1>;

        const EnhancedComponent = withMessage(MyComponent);


* WrappedComponent is a parameter passed into the Higher-Order Component function.


