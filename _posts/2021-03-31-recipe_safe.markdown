---
layout: post
title:      "Recipe Safe - Sinatra Project"
date:       2021-03-31 17:17:50 -0400
permalink:  recipe_safe
---


Since the start of Covid and being stuck in the house with not much to do, I started using a lot of my free time to bake. Also, I did a little bit of cooking in college but was constantly looking up different recipes to find which one was best. When it comes to cooking/ baking, there are many different ways and ingredients to get almost the same outcome. Whether the recipe was a healthier alternative or just more delicious, I always liked to save my favorites somewhere.

So to track my recipes I just made a page on the notes app in my phone called "Recipes" and would copy and past my favorites in there to look at the next time I wanted to make it. This got to be a lot once I had more than 5 recipes saved in my little notes page. It was tough to scroll through all of them and find which one I actually wanted to make.

So for my Sinatra project I decided it would be perfect to create a website where a User can store all their favorite recipes - called Recipe Safe! My program has 2 models to it - a User model and a Recipe model. A user has many recipes and a recipe belongs to a user.

For this app a user starts off by creating an account or they logging in if they already have one. They must sign up with their name, email and a password, and if the email is already associated with another user it just re-directs them to the sign up page to try again. Then they only need their email and password to log in again after that. If they type in the wrong email or password a flash message pops up telling them something was wrong and they need to try again.

Then once logged in they are able to create recipes that will be displayed in their recipe safe (index page). Each recipe has a name, ingredients, instructions and a cook time. Once a recipe is created it brings you back to the recipe safe where all your recipes are stored. Only the names of each recipe and an "edit" button are shown in the recipe safe. A user can click on the recipe name to see the full recipe or click "edit" to change the recipe however they'd like or delete it. 

It was really fun to build something like this since I have always struggled on where to keep my favorite recipes. I am excited to learn more about coding and be able to give it some extra features to perfect it!
