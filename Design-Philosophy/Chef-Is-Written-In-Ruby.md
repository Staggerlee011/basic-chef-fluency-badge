# Chef Is Written In Ruby 

> Candidates should understand:
> - How Chef uses a Ruby-based DSL
> - How to use raw Ruby to extend Chef	
> - What a library is

## How Chef uses a Ruby-based DSL
The Recipe DSL is a Ruby DSL that is primarily used to declare resources from within a recipe. The Recipe DSL also helps ensure that recipes interact with nodes (and node properties) in the desired manner. Most of the methods in the Recipe DSL are used to find a specific parameter and then tell the chef-client what action(s) to take, based on whether that parameter is present on a node.</br>

Because the Recipe DSL is a Ruby DSL, then anything that can be done using Ruby can also be done in a recipe, including if and case statements, using the include? Ruby method, including recipes in recipes, and checking for dependencies.</br>

https://docs.chef.io/dsl_recipe.html

## How to use raw Ruby to extend Chef	


## What a library is
A library is a ruby file used to either extend a class or create a new functionality in ruby for Chef. The library is in the root of the Chef-Repo along with the cookbook, roles, etc

[Return to Design Philosophy](README.md)</br>
[Return to Home](../README.md)
