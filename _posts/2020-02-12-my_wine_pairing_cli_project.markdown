---
layout: post
title:      "My Wine Pairing CLI Project"
date:       2020-02-12 19:48:22 -0500
permalink:  my_wine_pairing_cli_project
---


For my CLI Project, I decided to create a wine pairing app. The user inputs the wine they are drinking tonight and the app lets them know what food pair well with that wine. 

This project was a great experience for me. Working on a project really allowed me to see coding from a different perspective, and allowed me to tinker with learning how to change things that aren’t working, reading errors, and searching for new concepts that may help me (as well as concepts that I needed to review). I utilized an API in my project and used an API Request to inform users on what foods go well with the specific wines. Even though If you ask me anything about wine I’ll just say “Moscato goes with everything. It tastes great. Drink it until the cows come home.” 

 To make my program run successfully I accepted the user’s input on which wine they were drinking and then interpolated the input into the url for the API request 
 
 ```
 def self.get_pairings_for_wine(input)
  HTTParty.get "https://spoonacular-recipe-food-nutrition-v1.p.rapidapi.com/food/wine/dishes?wine=***#{input}***"
	``` 
	
and then accessed the description information from the returned hash and presented this to the user. They then had the option to enter another wine or exit the application. Then to clean up the app, I took a lot of the small behaviors, such as put-sing phrases and processing data and put them into their own methods. 

This project was challenging because sometimes I would take simple matters and over complicate them, and then after over complicating things, then I would forget simple techniques or methods that I learned a few weeks ago. Sometimes I just had to take a step back and realign my mind because everything was running together and seemed confusing. But once the app started functioning just a tad bit, things started to come together and started to make sense. 
