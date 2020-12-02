---
layout: post
title:      "React Bootstrap"
date:       2020-12-02 15:56:48 +0000
permalink:  react_bootstrap
---


After creating a basic React app, it seemed a little plain. It was rounded around the edges and was "presentable", but it needed some spicing up. I decided to use React Bootstrap to improve my app. The great thing about bootstrap react is that it has no dependency on bootstrap.js or jQuery. On top of that it was very simple! React-Bootstrap simplifies things by condensing the original Bootstrap into React-styled components. It makes your code very simple, short, readable, and straight to the point. 

The easiest way to add Bootstrap to your React app is by using BootstrapCDN. No installs or downloads required. Simple put a <link> into the <head> section of your app, like below, and you're good to go! 

```
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.0/css/bootstrap.min.css" 
integrity="sha384-9gVQ4dYFwwWSjIDZnLEWnxCjeSWFphJiwGPXr1jddIhOegiu1FwO5qRGvFXOdJZ4" 
crossorigin="anonymous">
```

I had to be careful though because  React-Bootstrap completely reimplements Bootstrap's JavaScript, it's not automatically compatible with themes that extend the default JavaScript behaviors. 
The good thing about React Bootstrap is that when you are importing bootstrap components, you will just import the individual components, as opposed to the entire library. This makes significantly less less code that we have to send through the client. Overall, I felt that React Bootstrap is very simple to use and really gave my app that "pop". 

