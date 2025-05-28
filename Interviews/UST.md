UST - 28/May/2025

* How to center a < div> using HTML/CSS?
* Why does .child still appear centered even when .parent doesn’t have position: relative?
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

---------------------------------------------------------------------------------------------------------
* Why does .child still appear centered even when .parent doesn’t have position: relative?
---------------------------------------------------------------------------------------------------------

                .parent {
                height: 500px;
                width: 500px;
                background-color: red;
                // no position: relative here
                }

                .child {
                height: 100px;
                width: 100px;
                background-color: green;
                position: absolute;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
                }

Because position: absolute elements are positioned relative to the nearest positioned ancestor (an element with position: relative, absolute, or fixed).
If no positioned ancestor is found, the .child gets positioned relative to the < html > (or body) element — the page itself.

---------------------------------------------------------------------------------------------------------
* To create a layout using Bootstrap that displays 4 items arranged horizontally on larger screens and vertically on smaller screens, you can use Flexbox + Bootstrap column breakpoints.
---------------------------------------------------------------------------------------------------------

                <div class="container">
                <div class="row">
                    <div class="child col-3"></div>
                    <div class="child col-3"></div>
                    <div class="child col-3"></div>
                    <div class="child col-3"></div>
                    <div>
                </div>