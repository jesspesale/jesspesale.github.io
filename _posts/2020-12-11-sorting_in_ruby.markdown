---
layout: post
title:      "Sorting in Ruby"
date:       2020-12-11 17:10:04 +0000
permalink:  sorting_in_ruby
---

While going through the Ruby section of the Software Engineering program, one very helpful built in method I used was .sort. This method is (quite obviously) used to sort a collection of data.

There are 3 different ways you can use the sort method and they are .sort,    .sort!  and  .sort_by
 

### (1)     .sort

This is the basic sort method that will compare all elemetns of the cllection using the sorting operator.


**The sorting operator <=> **

This is also knows as the spaceship operator.

It will take in 2 parameters and return one of the following 3 values:

* 0 if the two parameters are equal
*  -1 if the first parameter is less than the second parameter
*  1 if the first parameter is greater than the second parameter

(if the result is 0, the order of the elements is unpredictable and doesn't change)


So the sort method will sort integers from the smallest value to the largest (ascending order), and sort strings alphabetically. 
This will return a new array(or hash) with the results **without changing the existing array**. Sometimes you like to store the return value in a variable to keep for later.


EX:
[1, 25, 5, 15, 10, 20].sort

=> [1, 5, 10, 15, 20, 25]

or

arr = ['Banana', 'Apple', 'Mango', 'Passionfruit', 'Pineapple']

new_arr = arr.sort

   => ["Apple", "Banana", "Mango", "Passionfruit", "Pineapple"]

arr = ['Banana', 'Apple', 'Mango', 'Passionfruit', 'Pineapple']

new_arr =   => ["Apple", "Banana", "Mango", "Passionfruit", "Pineapple"]



Now the sort method works great just that way, but you can also pass in  an optional block if you would like and customize the way you want everything getting sorted. For example if you wanted to sort integers in from greatest to least (descending order)  you would do something like this:


[1, 5, 3, 7, 9].sort { |a, b| b <=> a } # => [9, 7, 5, 3, 1]



### (2)     .sort!


This method works the same way as just regular. sort, except it changes the original arrays values instead of creating a new one.

For example:

my_array = [9, 4, 3, 8, 7]

my_array.sort! = [3, 4, 7, 8, 9]

my_array = [3, 4, 7 ,8, 9]



### (3)     .sort_by

Lastly, the sort_by method must be called with a block that takes in an argument (or 2 for a hash). The syntax looks like this for the two:

sort_by { |obj| block } → array

sort_by { |x, y| block } → hash

This method will sort the data by mapping the values through the given block and returns the value in ascending order.

For example let’s sort an array by the length of the strings passed through

arr = ['Banana', 'Apple', 'Mango', 'Passionfruit', 'Pineapple']

arr.sort_by{ |word| word.length }

=> ["Apple", "Mango", "Banana", "Pineapple", "Passionfruit"]

Now if you wanted to sort it in reverse order (or descending) you can use the - instead of the reverse method

arr.sort_by { |word| -word.length }

=> ["Passionfruit", "Pineapple", "Banana", "Apple", "Mango"]

Lastly here is an example with a hash

hash = {a:1, b:2, c:4, d:3, e:2}

Now you sort it by just the values like this:

hash.sort_by {|k, v| v}

=> [[:a, 1], [:b, 2], [:e, 2], [:d, 3], [:c, 4]]


And thats the run down for those methods! Sort is a very helpful method to learn for Ruby and I am glad I took the time to understand the different forms of it.





