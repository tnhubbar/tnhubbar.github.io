---
layout: post
title:      "Need to Rent Some Baby Gear!!"
date:       2020-10-11 20:54:14 +0000
permalink:  need_to_rent_some_baby_gear
---


For my React-Redux Project, I decided to create a Baby Gear Rental Portal where one can come and find families willing to rent out their used baby gear. I myself have a toddler, and we have TONS of baby supplies. (Infant car seat, high chair, jumpers, bouncers, strollers, bassinets, you name it). These items are taking up so much space in my garage, but I don’t want to “throw them away” because in a year or two I’d like to have another baby. So how about I just rent the items out temporarily and then sanitize them afterward. That way, I can have the items when I need them and in the interim, rent them out. 
This project was by far the most difficult thus far because it included so many different concepts and required going back and researching a lot of knowledge that I previously learned (that slipped away a tad bit over time). The most difficult part of this project for me was redux! I felt that React was very simple and straightforward , and then came along Redux and pulled me in every which way. Storing our state locally in a simple application where you don’t have a lot of data is easy and simply. But when applications start getting complex, it is easier to store the data in an object separate from your components. Doing this will allow you to grab whatever you want for whichever component needs it at that time. With the help of a reducer, any component can easily update the data by dispatching an action telling Redux what to do. So I was able to tell Redux, hey, creating this new family” . And with the help of Provider and Connect, any React Component can connect with the store and get data from the store’s internal state, and get new data when that state changes. 
```
import React from 'react'
import {connect} from 'react-redux'
……..
export default connect(null, {addFamily})(FamilyForm)

```
In our instance above, we aren’t asking for any data, we are only sending data, so the first argument into connect is null, and the second argument is our addFamily action. We could have written this in a mapDispatchToProps function, but it was simpler in this case just to put it directly in there as an object and connect will automatically call dispatch. When creating and planning this app I told myself “Okay, I want to add a new family and they can enter in the items they’d like to rent out, how am I going to get this into my database?”Well, I can use a handy dandy fetch request, but wait, fetch requests are asynchronous and return an unresolved promise. So the action creator will return an action before the data is retrieved. This is where I needed a middleware called Thunk. Thunk allowed me to return a function inside of my action creator instead of a plain JavaScript Object. That returned function received the store’s dispatch function, and I was able to dispatch one action to place the state in a loading state, and another to update the store with the returned data. ```

import thunk from 'redux-thunk'
import {Provider} from 'react-redux'
import familyReducer from './reducers/familyReducer'
import {BrowserRouter as Router} from 'react-router-dom'

const composeEnhancers = window.__REDUX_DEVTOOLS_EXTENSION_COMPOSE__ || compose;

let store = createStore(familyReducer, composeEnhancers(
  applyMiddleware(thunk)
));

ReactDOM.render(
  <React.StrictMode>
    <Provider store = {store}>
      <Router>
    <App />
    </Router>
    </Provider>
    </React.StrictMode>
  ,
  document.getElementById('root')
);

``` 

Overall, this project was very complex, and involved A LOT of moving parts. To be honest, I feel building this project with rails would have been muuuuch easier. Haha. But I’m happy that I took the time to understand React and Redux, and I definitely foresee building many other apps with them and using code from the many libraries they provide. Now come and rent my baby gear please! I need to park in my garage. 
