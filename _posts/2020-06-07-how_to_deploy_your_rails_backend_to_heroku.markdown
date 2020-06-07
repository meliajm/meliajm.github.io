---
layout: post
title:      "How to deploy your Rails backend to Heroku"
date:       2020-06-07 13:58:40 -0400
permalink:  how_to_deploy_your_rails_backend_to_heroku
---


The purpose of this blog is to explain how to take your local Rails backend and deploy it to Heroku. Here, we are starting with a repo on github that was created with `rails new <name of app> --api` and assuming you've got an Heroku account or can set one up. Heroku allows for 5 or so free apps.

First thing is to update the Gemfile. Heroku does not allow `sqlite3`, instead we've got to use `postgres`.

The Gemfile should contain this:
```group :production do 
  gem 'pg', '~> 0.18.4'
end```

and something like this:
`group :development, :test do
  gem 'byebug', platforms: [:mri, :mingw, :x64_mingw]
  gem 'sqlite3', '~> 1.4'
end`

Now let's `bundle install`.

To config/database.yml add:
`production:
  # <<: *default
  adapter: pg
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  timeout: 5000
  database: backend-example-production
  username: backend-example
  password: <%= ENV['BACKEND-EXAMPLE_DATABASE_PASSWORD'] %>
  # username: example-api-ge-heroku-example&#x2028;  password: <%= ENV['EXAMPLE-API-GE-HEROKU-EXAMPLE_DATABASE_PASSWORD'] %>
`

Once we've got our frontend deployed as well, we will need to change config/initializers/cors.rb to:

```origins 'nameofsite.com'```

   

Make sure your repo is updated on github. And it is a good idea to make sure you are able to run your server locally before deploying so that everything is what you expect it to be.

Next we are going to start with Heroku:
1. `heroku login`
2. Follow instructions
3. `heroku create`

For the moment of truth:
4. `git push heroku master`

I like to populate the database using the console

5. `heroku run rake db:migrate`
6. `heroku run rails console`
7. Seed your database how you see fit 
6. Visit your site

For additional resources see: https://devcenter.heroku.com/articles/getting-started-with-rails6

And that's it for the backend!

