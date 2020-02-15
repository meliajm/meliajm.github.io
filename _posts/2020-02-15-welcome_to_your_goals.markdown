---
layout: post
title:      "Welcome to your goals "
date:       2020-02-15 17:19:12 +0000
permalink:  welcome_to_your_goals
---


Hi there! For this project, I used Sinatra and Active Record to build a web application. How cool!

The idea for this web app is for a user to be able to write their goals and when they would like to complete them. They can also keep track of how many goals they have accomplished by seeing the percentage completed. Eventually, I'd like to use a calendar to have daily goals and color coordinate them to different topics or areas. So for example, if on Monday the user has a goal on working out, that might be in blue. This way the user can see trends over time for their life.

For this app, I built a user and goal relationship where a user has many goals and a goal belongs to a user. A user should only be able to edit and view their goals. A user can signup and login, create goals, see them listed, edit a goal, and delete a goal. The user can also check if the goal is completed and this will add that goal into a new column of completed goals. In building this I added a little bit of CSS to have 2 columns next to each other.

Issues I ran into for this project were I forgot to add the password type as password for input in HTML and wasn't getting the dots to show up for the password. I hadn't figured out how I was going to use the checkbox for completed goals and how to save that information. I ended up adding an additional attribute to goals called completed so that once checked that would turn completed "on" and I could use that attribute for logic on the goals page listing a user's goals. Another thing I wasn't sure about is all of the logic I put into the erb file for the goals page. I know we want to have a separation of concerns, so maybe it would be better to have a bigger Goal class. For now, though I wanted to get it working and I can improve efficiency as part of future works. It was a little tricky to pre-populate the by when date because we need the exact string.


In addition, this was the first time I used multiple branches on Github. And I don't think I've got that down. I haven't figured out how to merge two branches back together yet. I did a pull request and git merge but that did not work.

I learned about errors in the browser. For example, if you navigate to a goal in the address bar as opposed to using the links in the browser and you stumble upon one that has been deleted or not created yet, you'll see nil and NoMethodError.

Another takeaway is to remember to add any additional attributes to the create or update lines in your code. I was forgetting this and couldn't understand why the by_when attribute wasn't showing up. So even if everything is correct in the view, the controller has to have that property there as well.

I also got much practice with rake and databases. I deleted the development and schema files many a time.

I am grateful help from my cohort leads, Howard and Enoch and as well as cohort members including Allison. Thank you for all your help!
