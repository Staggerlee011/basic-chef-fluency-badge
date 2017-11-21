# Cookbooks

> Candidates should understand:
> - Cookbook contents	
> - Naming conventions						
> - Cookbook dependencies	
> - The	default	recipe	

## Cookbook Contents
### .delivery (folder)

### Spec (folder)
	Has a unit folder, which has a recipes folder ChefSpec tests
	
	default_spec.rb

### Recipes (folder)
	Collection of ruby tasks that control what the 

### .kitchen.yml
	Config file for how to the cookbook can be tested (driver config etc)

### .kitchen (folder)
	Contains output details of test-kitchen runs

### Metadata.rb
	Manage the metadata about a package. This includes things like the name of the package, a description, etc.
	
	It also includes things like dependency information, where you can specify which cookbooks this cookbook needs to operate. This will allow the Chef server to build the run-list for the nodes correctly and ensure that all of the pieces are transfered correctly.
	
### Berksfile
    Used to pull related cookbooks from the supermarket or from local Chef Server

### Templates (folder)

### Test (folder)
    Folder to contain InSpec tests, when using `chef generate recipe xxx` it will create a test file with the same name. 
	Has a smoke folder, which has a default folder
	
	Default_test.rb
        Starter rb file for InSpec tests

### chefignore

### README.md
    Readme file 

## Naming Conventions
###Cookbook Naming
Use a short organizational prefix for application cookbooks that are part of your organization. For example, if your organization is named SecondMarket, use sm as a prefix: sm_postgresql or sm_httpd.

### Use of Hyphens¶
Cookbook and custom resource names should contain only alphanumeric characters. A hyphen (-) is a valid character and may be used in cookbook and custom resource names, but it is discouraged. The chef-client will return an error if a hyphen is not converted to an underscore (_) when referencing from a recipe the name of a custom resource in which a hyphen is located.

### Cookbook Versioning
	• Use semantic versioning when numbering cookbooks.
	• Only upload stable cookbooks from master.
	• Only upload unstable cookbooks from the dev branch. Merge to master and bump the version when stable.
	• Always update CHANGELOG.md with any changes, with the JIRA ticket and a brief description.

From <https://docs.chef.io/ruby.html> 


## Cookbook dependencies
Recipes can link together to isolate actions. 

Cookbook to Cookbook (DEPEND / INCLUDE_RECIPE)
For a cookbook to DEPEND on another cookbook (ie a cookbook that runs apt-get update, is needed before installing nginx) you need to make the following changes:

In recipe.rb file (can be default or named)
`include_recipe "apt"`

In metadata.rb for cookbook 
`depends "apt"`
	You can also set it to version specific 
`depends 'cats', '< 1.0'`

Recipe Linkage
To add a recipe and link it to default you will need to create the recipe (chef generate recipe myNewrecipe). And update the default recipe with 

`include_recipe 'wisa::lcm'`

	Where wisa is the name of the cookbook and lcm is the name of the recipe
	To add multiple you just add a new line no , or separators are needed ieL

`include_recipe 'wisa::lcm'`
`include_recipe 'wisa::web'`

	When mulitple recipes are added they are ran in order (top to bottom)


## The default recipe
Can either include a recipe or link to other recipes in the cookbook. BP is to create separate recipes (`chef generate recipe xxx`) for isolation.


## Links
[Chef Docs - Cookbooks](https://docs.chef.io/cookbooks.html)


[Return to Chef Basic Terminology](README.md)</b>
[Return to Home](../README.md)