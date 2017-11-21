# Explicit Actions

> Candidates should understand:
> - How Chef uses explicit actions and only does what you tell it to						
> - Actions for common resources such as the :nothing action
> - What it means to roll back infrastructure
> - What happens if you reverse the order of resources in a recipe
> - If Chef can automagically detect what patches should be applied to a system

## How Chef uses explicit actions and only does what you tell it to
Chef works on test and repair, This means that if you create a cookbook to create a file called Test with the text "This is my text". If someone logs into the server and updates that text to "my new text", the next time the chef-client runs it will revert the text back. 

But if someone changes the permissions of the file. Chef will not do anything. As you have not explicitly defined what the security of the file should be.


## Actions for common resources such as the :nothing action


## What it means to roll back infrastructure
A roll back in Chef if not advised and you should aim to roll forward. If you do need to roll back you would need to update the recipe to use the previous version and deploy that.

The better solution would be to create a fix and update the version of cookbook forward. 


## What happens if you reverse the order of resources in a recipe
The recipes will run in reverse order


## If Chef can automagically detect what patches should be applied to a system
No idea what that means.. You can check for updates in windows 2016 using CIM methods. and in Linux via running apt-get update. Both could be put into a recipe. but im not sure it would logically.


[Return to Design Philosophy](README.md)</br>
[Return to Home](../README.md)
