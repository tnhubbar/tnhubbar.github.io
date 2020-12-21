---
layout: post
title:      "Benefits of React Hooks"
date:       2020-12-21 02:31:37 +0000
permalink:  benefits_of_react_hooks
---


Previously, we had two ways to create components. We could use classes or functions. The difference was that if our component had state or needed to utilize a lifecycle method, we had to use a class. But when we have to do things like include animations, form handling, and connecting to external data source we end up with huge components that are hard to refractor, duplicated login, and complex patterns. Otherwise, if it just accepted props and rendered some UI, we could use a function. But what if we wanted to always use a function, even when we did need state or needed to utilize a lifecycle method? This is where React Hooks comes in. Using hooks, we no longer have to call super(props) and we also no longer have to worry about binding  our methods to the this keyword. We can now apply logic "inside" the component, rather than just between the components. 
