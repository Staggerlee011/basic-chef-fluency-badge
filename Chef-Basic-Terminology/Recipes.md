# Recipes

> Candidates should understand: 
> - What a recipe is 
> - Importance of the resource order 
> - How to use 'include_recipe' 
> - What happens if a recipe is included multiple times in a run_list 
> - The 'notifies' and 'subscribes' directives 

## What a recipe is 
A recipe is the most fundamental configuration element within the organization. A recipe:
- Is authored using Ruby, which is a programming language designed to read and behave in a predictable manner
- Is mostly a collection of resources, defined using patterns (resource names, attribute-value pairs, and actions); helper code is added around this using Ruby, when needed
- Must define everything that is required to configure part of a system
- Must be stored in a cookbook
- May be included in a recipe
- May use the results of a search query and read the contents of a data bag (including an encrypted data bag)
- May have a dependency on one (or more) recipes
- May tag a node to facilitate the creation of arbitrary groupings
- Must be added to a run-list before it can be used by the chef-client
- Is always executed in the same order as listed in a run-list

From <https://docs.chef.io/recipes.html> 

## Importance of the resource order 

Resources (code or configuration in the recipe) are ran in chronological order from top to bottom. If you need a folder to be created for a file. You will need to create folder first then create the file. 

## How to use 'include_recipe' 

Example usage (Load single recipe):
`include_recipe 'wisa::web'`
	Which includes the web.rb recipe from the wisa cookbook

Example usage 2 (Loading multiple recipes)
`include_recipe 'wisa::lcm'`
`include_recipe 'wisa::web'`
	Note that no seperators are needed
	Recipes are ran in order
	If the same recipe is called multiple times it runs the first one and ignores rest 


## What happens if a recipe is included multiple times in a run_list 

If a specific recipe is included more than once with the include_recipe method or elsewhere in the run_list directly, only the first instance is processed and subsequent inclusions are ignored.

From <https://github.com/chef/chef-web-docs/blob/master/chef_master/source/recipes.rst> 


## The 'notifies' and 'subscribes' directives 






