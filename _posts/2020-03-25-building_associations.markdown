---
layout: post
title:      "Building associations"
date:       2020-03-25 20:46:27 +0000
permalink:  building_associations
---


Alright, so you want to build a new object that is associated with another object? In my Rails project, I have a User class and a User has_many Bentoboxes. A Bentobox belongs_to a User. So if I want to build a Bentobox associated with a User, I can do this (in the console for example):

```
# First, you need to know which User you want:
user = User.find(4) # you need to know the id in this case

# Next, build the association, starting with the class that has many so in this case User:
new_bento = user.bentoboxes.build(name: "test_name1", bento_type: 'Lunch') 

# Lastly, save!
new_bento.save
```

And that's it!

