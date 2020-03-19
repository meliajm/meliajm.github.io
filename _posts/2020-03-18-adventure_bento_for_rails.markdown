---
layout: post
title:      "Adventure Bento for Rails"
date:       2020-03-19 03:20:17 +0000
permalink:  adventure_bento_for_rails
---


For this blog, I thought I would detail not my thought process for building this rails 'Adventure Bento' web app, but instead showcase how the requirements are passing. Really a way for me to example the feature of the my app in a somewhat organized what and make sure all of the requirements are met.

A brief overview: my sister thought it would be a fun food cart to have customizable bento boxes. So here is her website before the cart. A user can look at the menu; the menu consists of signature or specialized bento boxes and the option to make your own. Choose your own adventure! The bento boxes are made up of menu items. The user can review her order and place her order. 

First one is: using Ruby on Rails. Check. Done. Let's move on.

Includes one has_many relationship. Okay for this I've got a bunch because I have two sets of join tables. A menu item can be in many bentos and a bento can have many menu items. At first I did not have this many to many relationship set up and this meant a menu item could only be in one bento box. Not what I wanted!

Include at least one belongs_to relationship: An order belongs to a user. Here this is what we want because for every order it will only have one user. Orders won't be shared like menu items are.

Include at least two has_many through relationships and Include at least one many-to-many relationship (got 2 many-to-many): okay here is the join table. Bentos, we've got this! Bento has many bento_menu_items (this is the join) and menu item has many bento_menu_items. So we can get that all too good many to many relationship. Same idea for bento and order. Bentos can be in many orders and orders can have many bentos. Woooo!

The "through" part of the has_many through includes at least one user submittable attribute: here I use order which is a join table so the through part...

Include reasonable validations for simple model objects: validates presence and uniqueness were needed as well as making sure at least one item is checked. For example, an order needs at least one bento box. I could also add something where only one entree is allowed in a bento or if there are multiple entree, then have the price change by more than just the price of however many entrees. 

Include a class level ActiveRecord scope method Class: I use order_array_by_item_type as a class method to call on menu items so that the item type is ordered alphabetically when listed on the indices. It does not have its own url though. Total price does have a url but total_price is not a class method; it is an instance method.

Include signup, login, logout + Include third party signup/login: a user can do all of these through the website and login with github using OmniAuth.

Include nested resource show or index + Include nested resource "new" form: orders is nested into users for show, index, and new.

Include form display of validation errors: Validation errors and flash notices are displayed.

Views use partials if appropriate: partial and partials with locals are used because the menu shows bentos and past orders calling for partials. Partials are used as forms as well.

Limited logic in controllers +  The application is pretty DRY: sessions controller has the most logic. Methods have been added to keep things DRY.

Helper method are used for current user and logged in.
