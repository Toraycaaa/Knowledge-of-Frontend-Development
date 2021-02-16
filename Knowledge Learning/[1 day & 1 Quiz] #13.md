





## [1 day & 1 Quiz] #13

***

*13/02/2021*

**Question:**

 What are the three phases of ==<u>event propagation</u>==? 

A: Target > Capturing > Bubbling
B: Bubbling > Target > Capturing
C: Target > Bubbling > Capturing
D: Capturing > Target > Bubbling

**Answer:** D

**Taps:**

==Event Propagation (Event Bubbling)==:  

Event propagation is a way to describe the “stack” of events that are fired in a web browser. When a event has been fired, it will be propagate from parent elements to child elements.

(Example: https://www.freecodecamp.org/news/a-simplified-explanation-of-event-propagation-in-javascript-f9de7961a06e/)

==Three phases:==

**Capturing(Trickling):** propagate from window object to target object.

**Target:** fire ot trigger the event in target object.

**Bubbling:** The movement of events “up” from the most-nested element.( If events start in the “outer-most” element and moved “down,” that is referred to as “trickling.”  滴流)

Bubbling: Inner-most -> Outer-most 

Trickling: Outer-most -> Inner-most

During the **capturing** phase, the event goes through the ancestor elements down to the target element. It then reaches the **target** element, and **bubbling** begins.

[![img](https://camo.githubusercontent.com/5fd2d347d044150e4ae35091622f0628f0eb7893966f03c8955ca271f3153e47/68747470733a2f2f692e696d6775722e636f6d2f4e31386f5267642e706e67)](https://camo.githubusercontent.com/5fd2d347d044150e4ae35091622f0628f0eb7893966f03c8955ca271f3153e47/68747470733a2f2f692e696d6775722e636f6d2f4e31386f5267642e706e67)

**Relating DOM:** 

event.stopPropagation(): https://developer.mozilla.org/zh-CN/docs/Web/API/Event/stopPropagation

event.preventDefault(): https://developer.mozilla.org/zh-CN/docs/Web/API/Event/preventDefault

