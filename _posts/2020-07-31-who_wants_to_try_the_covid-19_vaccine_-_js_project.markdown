---
layout: post
title:      "Who wants to try the COVID-19 vaccine - JS Project"
date:       2020-08-01 00:00:29 +0000
permalink:  who_wants_to_try_the_covid-19_vaccine_-_js_project
---


The content of your blog post goes here.
The Single Page Application that I created was a patient randomization application. This project was designed to mimic a COVID-19 clinical trial where a patient is randomly assigned to the Trial Vaccine or to Placebo, and then given a patient ID number. (They can only see Treatment A or Treatment B, so they won’t know which one they have to prevent bias) On the page it can be shown how many people are assigned to Treatment A and how many are assigned to Treatment B. They can also delete that patient if they no longer wants to participate. This project was very interesting to me because for a very long time I kept trying to figure out where exactly Javascript tied into Ruby on Rails. I wasn’t grasping where they were connecting, and how to pull them together. Finally at the end I realized the fetch request is where we bridge the gap. The fetch returns a promise and then we can process that down and manipulate it how we’d like and add it to the DOM. This is where I hit the most challenges. The hardest part of the entire module for me was grabbing elements from the DOM and also inputting data into the DOM. I felt like there were a million ways to skin a cat when it came to displaying items on the DOM. There’s template literals, one could appendChild, or one could add the empty containers into the html file, grab that container, and add the data into the innerHTML of the container. My personal favorite was creating the empty container in the html file and then just adding to it: 

```let statArea = document.querySelector('.stats')

        statArea.innerHTML += 
				`<div id=${this.id}> Patient ID: ${this.id} <button type="button" class="button" id="${this.id}" >Withdraw/Lost to Follow Up</button></br></br></div> ```
				
The other challenging piece of this project was iterating through the data of the returned object from the fetch. My data came back as an array of objects, and I need to iterate over each object and display specific attributes from within. 

```patients.forEach((person, index, array) => {
                let patient = new Patient(person.id, person.name, person.dob, person.gender, person.factors, person.effects, person.treatment.id, person.treatment.name)
                console.log(patient);
                patient.renderPatient()
            })```
						
						
  After much practice and tinkering around I finally wrapped my head around an overall flow of using Javascript to manipulate the frontend and using Rails as an API to do work on the backend. On the frontend, we’re creating functions that will be invoked when the events are triggered from our event listeners. We can use fetch with CRUD actions and GET, POST, PATCH, or DELETE to connect with our backend to process sent data which then returns data back to us that we can use.
	
	
	```function sendData(newPtData){
    let configObj = {
        method: "POST",
        headers: {
        "Content-Type": "application/json",
        "Accept": "application/json"
        }, 
        body: JSON.stringify(newPtData)}
    
    fetch("http://localhost:3000/patients", configObj)
    .then(resp => resp.json())
    .then(enteredData => {
        let patient = new Patient(enteredData.id, enteredData.name, enteredData.dob, enteredData.gender, enteredData.factors, enteredData.effects,  enteredData.treatment.id, enteredData.treatment.name)
                console.log(patient);
                patient.renderTreatment()```****
	
And all of this happens without the page rerouting or reloading. This makes for a much better user experience. 
Overall, of all projects, I liked this project the most because it resonated with current events and my current career. I also enjoyed this module because I was able to compare Ruby vs. Javascript. Originally I only had Ruby in my toolbox, so I didn’t know anything different. But now having Javascript, I see how they are similar and the pros and cons of each one. 
