---
layout: post
title:      "Board Game CLI"
date:       2019-12-30 17:43:59 -0500
permalink:  board_game_cli
---



Hey there! This blog is going to go over my thought process for building my first BIG command line interface (CLI).

First I looked at all the requirements and watched a video from Flatiron on this topic. I wanted to have a good understanding of the big picture as well as how all the smaller parts were connected without understanding everything to start. I checked out the main example on github.com on restaurants and was able to get a pretty good grasp while still not really knowing what I was going to be building. Haha. I had forked and cloned a repo that I thought I could start with but that turned out to not be the best way. Instead, using bundle gem name of gem is the way to go.

From here, I had the skeleton of what I needed to get building. I put some notes together of what I wanted the user to be able to do. Basically, I wanted to get board game info from a website on top board games and give some criteria on these games such as the number of players, length of game, and important data like that. After a bit of searching, I found such a website that listed the board games, gave a description, and had stats on each game in a pretty consistent format for each game. There were some inconsistencies from the website such as having 20 games and only giving 19 ages and things like that. But we can live with this.

The first thing I did actually was do a 30-minute video of me working through the start of my project. I haven't gone back and watched it yet but I imagine it is pretty funny. In those 30 minutes, I set up the gem from bundle and started my CLI, board game class, and scraper class. Afterward, I got the console up and running so that I was able to use irb. I mostly utilized pry but it's nice to have options. The console was broken at first because of some dependencies.

Scraping: This was a bit of a problem because I was not able to get each stat for every game like I imagined would be best but instead a giant string of all the names and age and other criteria. I was scrappy in my scraping and made it work through string manipulation. It's probably not the best way to go out it but it gets the job done. And the focus on the project is not on scraping so I did not want to focus too much on this.

BoardGame: The board game class is pretty straightforward. Just have to make sure we've got a way to see all those criteria we keep talking about.

CLI: Here is where the fun is! After scraping and get the board game info and being able to actually populate these objects with data from the website, we can sort info to be useful for the user. Let's say you've got a game night and want to check out a new game. You're not sure which game to choose although you've got this neat CLI that has board game objects that you can ask questions to. Maybe you want to know "What games are the most challenging?". You can search for that. Maybe you want to know "What games can I play with 4 players?". You can ask that as well. Lastly, you can ask "If I know the age of the youngest person, the challenge level of the group, and the number of players, what games meet my requirements?".

I was able to use mass assignment but not super, extend, or include. Until next time!



