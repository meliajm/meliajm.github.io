---
layout: post
title:      "Building a javascript frontend and rails backend"
date:       2020-04-15 22:51:11 -0400
permalink:  building_a_javascript_frontend_and_rails_backend
---


Alright doing something new again this time for my blog.

I have met my requirements for my single page application and the app is looking pretty good and performs mostly how I want. There are a few things that I would like to improve upon. Mostly related to presentation or UX. Instead I want to focus my energy elsewhere.

I am actually going to make a whole new project. That is more basic. I am thinking of doing Cats and Kittens or something like that. So that I can get more practice with javascript and building using object orientation and separation of concerns. And building in layers instead of all models at the same time, all migrations at the same time, and all of that. And focus my attention on the concepts of this section and not so much on styling. 

Explain how Rails routes a request to a controller and method based on the URL and HTTP verb
Use render json: to render serialized JSON
Select, Create, and Modify DOM nodes
Attach listeners to DOM nodes to respond to user interaction
Use preventDefault to control form submit behavior
Use fetch with 'GET', 'POST', 'PATCH' & 'DELETE' HTTP methods
Create a JavaScript object with ES6 class syntax
Instantiate JavaScript objects and call methods on them.

Okay here we go! Let's do this!

First I am going to make a new project with 
> > rails new task-manager --api
>

Make sure to add the api flag.

Next make sure cors is set up in the gem file and config folder:
> gem 'rack-cors'
 bundle install
>

In config/initializer/cors.rb
> 
Rails.application.config.middleware.insert_before 0, Rack::Cors do
  allow do
    origins '*'

    resource '*',
      headers: :any,
      methods: [:get, :post, :put, :patch, :delete, :options, :head]
  end
end
>

And let's push to github:
-Create a new repo on github with a fun name
git add .
git commit -m 'some message'

Then use the code under this header on github one line at a time:
…or push an existing repository from the command line

Great now we all set up and ready to start scaffolding. Let's build!

Next I've got to start scaffolding:
> rails g scaffold Category name:string
> 

We are going to build vertically for this and use OOJS to start once on the frontend.

And check out our routes: looks good there since we've got our resources.

Add this to our Category class
>validates :name, presence: true

Check on controllers next. Don't need to worry about views as of now. Controllers are fine for now. I will need to change and add more to the Task controller actions and includes so that a task's category will show up too.

Don't forget to rails db:migrate!

Next we will confirm Category is working on the backend using rails console. I am able to create categories in the console. Let's see what's at localhost:3000/categories when the rails server is up and running.

Awesome! The 3 categories I made in the console are visible there!

And then we will be able to start on the frontend. Let's make a new directory called client to hold on things frontend.
mkdir client

Then start populating that directory with an index.html and javascript files.
>touch client/index.html
mkdir client/src
touch client/src/index.js
touch client/src/taskList.js
touch client/index.css
touch client/src/task.js
>touch client/src/api.js

In the html file, we add html:5 to build out the document. And add script src to this as well, so that we can utilize our javascript files. Yay!

Like this:
<script src="src/index.js"></script>

Let's go over these briefly: index.css is for styling, the src folder holds all of our scripts. The scripts are separated by concerns namely: api that will deal with all fetches, index is our main set up where everything comes together, taskList will organize the listing, while task will just deal with a given task. And that's it for the frontend file structure.

Let's make sure our js files are connected to the html file. We can console.log('here') for example and see if that is logged in our browser. It is!

Okay next thing I think is to actually do some fetching! Here's how we do that. Add the following to api.js:

const url = 'http://localhost:3000/categories'
fetch(url)
  .then(response => response.json())
  .then(jsonResponse => console.log(jsonResponse))
	
	Sweet! We are all set up for this layer of Category. 
	
	I think the plan of action forward is to scaffold task and go through the same process. Then start using object oriented js to build the DOM once we've got everything we need.

For this I will mostly summarize and not go into as much detail as category had.
rails g scaffold Task content:text category_id:integer completed:boolean
rails db:migrate

Add relationships to models and any validations, then add includes to controller actions and check strong params.

The Task controller takes more work than Category.

Create task in the console. See them up and running on the server.

Build classes on frontend!



