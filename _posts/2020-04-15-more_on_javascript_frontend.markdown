---
layout: post
title:      "More on javascript frontend "
date:       2020-04-16 02:52:42 +0000
permalink:  more_on_javascript_frontend
---


So for this blog I am going to write about building in layers or vertically in opposition to building similar things at once or horizontally. And next I will cover some javascript topics such as scope and hoisting.

Here is my somewhat high level over view of how to build in layers. For my project I've really only got two layers to build. What I'm calling a layer is basically models on the front and/ or back end.

To start create a new rails app with the api flag, add cors to your gem file, and make sure the initializer for this is set up, then scaffold the first model. I started with Category because it has many tasks. Check the routes, model, and controller actions. Test out the model in the console, create some seed data there. And connect to your server to see if your data from the console is there. If everything there looks good, you're ready to move on over to the frontend.

Okay so on the frontend, build out the file structure with scripting files, styling, and the html file where everything takes place. Make sure the scripting files are connected to your html file. You can console.log something in the scripts and make sure that appears in the browser in the console.

Next you want to make fetch calls to the backend to make sure those sides are talking properly.

Afterwards you are ready for some object oriented javascript!

For javascript, let's cover some topics.

Variable are set with const or let. They can hold numbers, objects, functions, and more.

Data structures are things like objects or arrays. Functions are also objects and have methods to call on functions (example toString and this just outputs the text of the function as a string, others are bind, call, and apply.)

Bind locks the this in place so that the function's arguments does not change. And bind is a confusing topic. Still learning. 

Here are my takeaways from frontend programming in javascript. You've got to do a lot twice if you use one source of truth on the backend. What I mean by this is related to updating and refreshing the page. Let's say you make a change to the DOM and then also makes a change to the backend as in something is updated. In my app this is if a Task is completed or not. The default value for all tasks is false, and once you click the completed button then the value changes in the database on the DOM. BUT if you don't tell your frontend to render this properly, then there will not be a change, so you'll have to build the new way of rendering again.

Currently I am having an issue with this exactly. And it's giving me some trouble. So here's the situation. When I log in as a user, the user's task show up all nice like they should. However, when I refresh the page, my frontend for some reason thinks that it does not know who the user is at the very beginning and for that reason cannot load the user's tasks which makes sense. I think this is related somehow to the way I am calling some of the fetches but I am not sure. 
