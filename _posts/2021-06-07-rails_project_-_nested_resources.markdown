---
layout: post
title:      "Rails Project - Nested Resources"
date:       2021-06-07 16:18:05 -0400
permalink:  rails_project_-_nested_resources
---


The ‘resources’ syntax in Rails is a useful way to generate each of the CRUD routes. It will create all 7 routes for our actions (index, create, new, edit, update, show, destroy).

Nested routes/ resources are a good way of representing a belongs to and has many relationships in Rails. I struggled with nested resources during the lessons and labs at Flatiron, so I decided to write my blog post for my Rails project on how I implemented the nested resources inot my application.

For my Rails project I created a Restaurant Review website. A user can sign up/ log in, add restaurants and review any of the restaurants (created by them or others). For the nested resource for my project, I thought the perfect scenario would be to be able to view all the reviews for a particular restaurant. Since Restaurants has_many :reviews and a review belongs_to :restaurant, a review is technically considered the child object to a restaurant so it will be the nested resource under the restaurant. The code in my routes file looks like this:

```

  Rails.application.routes.draw do

      resources :reviews
			
       resources :restaurants do
	           resources :reviews, only: [:new, :index]
       end
			 
   end
	 ```

Notice we have the nested routes for :reviews under restaurants, but then we also have the regurlar :reviews routes outside of the nested so people can still edit, create and view reviews outside of the context of the specific restaurant.

The route that I will use for this nested resource would be:

`Restaurant_reviews	 GET 	/restaurants/: restaurant_id/reviews        	reviews#index`

And when were writing the link, our URI helper needs to take in a specific restaurant as an argument, so it would be something like this:

     ** Restaurant_reviews_path(@restaurant) **
		 
Then in my reviews controller I made a conditional to account for whether the user is trying to see all of the reviews, or all the reviews for a particular restaurant:
```
    def index
        if params[:restaurant_id]  
              @restaurant = Restaurant.find_by_id(params[:restaurant_id])
              @reviews = @restaurant.reviews
        else    
            @reviews = Review.all
        end
    end
		```
		
So if the restaurant_id is in the params, it finds all the reviews for that restaurant. Otherwise it just lists all the reviews that are saved in the database.
		
I definitely feel more comfortable on this topic after doing some extra research and writing this blog post on it, so I am going to try to do the same for future topics that are confusing to me at first. Happy coding 😊
		
		
		
		 
		 
		 




