UST - 28/May/2025

* How to center a < div> using HTML/CSS?
* Position in CSS 
* Diff position: relative and position: absolute
* To create a layout using Bootstrap that displays 4 items arranged horizontally on larger screens and vertically on smaller screens, you can use Flexbox + Bootstrap column breakpoints.
* Why we are using the SCSS?
* Difference between SCSS and LESS?
* What is @mixin in SCSS, syntax?

---------------------------------------------------------------------------------------------------------
* How to center a < div> using HTML/CSS?
---------------------------------------------------------------------------------------------------------
 index.html

                <div class='parent'>
                    <div class='child'></div>
                </div>

styles.css    

First Way-
----------
                .parent{
                height: 500px;
                width: 500px;
                background-color: red;
                display: flex;
                justify-content: center;
                align-items: center;
                
                }
                .child{
                height: 100px;
                width: 100px;
                background-color: green;
                }

Second Way-
-----------
                .parent{
                height: 500px;
                width: 500px;
                background-color: red;
                position: relative;
                }
                .child{
                height: 100px;
                width: 100px;
                background-color: green;
                position: absolute;
                top: 50%;
                left: 50%;
                transform: translate(-50%,-50%);
                }