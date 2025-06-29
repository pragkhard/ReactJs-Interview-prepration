render props is a pattern are designed pattern in react where a component's logic is encapsulated in a prop that the component calls to render is output. So like that's a lot of theory, right? So let me explain in simple words. So, basically, we have this component over here, toggle label component, right? And if I show you the final app first, if I click on it, they simply just shows a message over here, right? Shows or hides, the message. 

![alt text](image.png)

![alt text](image-1.png)


And inside of this component, we have this div with the state over here isOpen and whenever we click 

![alt text](image-2.png)

we click on this button, it either hides or shows this particular message with respect to this is open pin. Okay. Now, imagine a scenario where we had to reuse this component again and again. This logic to remain the same but this thing to change, right? Or probably we can have something else as well over here, but certain certain part of this prop to change, So that is where render props comes into the picture. You can consider it more of, you know, code reusability, and it makes our code more flexible. So let me show you