---
layout: post
title:      "Plan Your Next Trip with my Excursion Creator!"
date:       2020-04-11 19:47:28 +0000
permalink:  plan_your_next_trip_with_my_excursion_creator
---


For my Sinatra project, I built an excursion creator. A user can create their own individual username with a password and they will have login capabilities. After logging in, the user can create excursions with places. For example, I could create an east coast fishing excursion and add Miami, Gulf of Mexico, and Jacksonville Beach as places to fish. It will then be saved in the database and accessible at a later time when that user logs in. This project was somewhat difficult because I learned a lot of new concepts in a short amount of time and had to correctly implement them. An interesting concept that I used in my project was Nested Forms. Because  I wanted both the excursion and the place to be objects, I had to make a form that created multiple objects at one time. The forms are where the objects are created, and we can’t have two keys with the same name, so we have to nest one of the objects into the other(owner) object . This way when the params hash is accessed in the controller, we can create both objects from that hash. 
	The next tough thing was that there could be “multiple” places in one excursion, so our places hash would have to store an array of nested hashes. This is where things got fun. ERB syntax made my life really easy! Instead of having to manually index through each entry, I was able to use an empty array ([]) and ERB automatically indexed the array for me and went through it. 
``` excursion[places][][activities] ``` 
So instead of having to do. ``` excursion[places][0][activities]``` for the first place and then ``` excursion[places][1][activities]```
for the second place, ERB will automatically identify the empty bracket and iterate through it. 

Then in the controller I could access the excursion data by ``` params[:excursion] ``` and I can access the places data by ``` params[:excursion][:places] ```. 

Another aspect of my project that I thought was interesting was ensuring that the only person who could edit the excursion was the person who actually created it. I’d be upset if I researched all the fun things to do in Japan and someone came in and wiped it all out! To do this, I used a helper class and in that class I created a class method  that identified who the current user was. 
``` def self.current_user(session)
        User.find_by(id: session[:user_id])
    end
``` 
I then compared this to the excursion’s user and if they matched, then that person can delete or make modifications to the Excursion. 
Overall, I felt this project was a great way to exercise my newly developed coding muscles and create something useful. Next time I’m planning a trip, I might just hop over to this application and plan away. 

