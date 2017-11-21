# Publishing Artifacts To Chef Server and Supermarket

> Candidates should understand:
> - How to publish artifacts to Chef server
> - What Berkshelf is
> - If the Chef Automate workflow feature can push artifacts to things other than a Chef server or Supermarket
> - How to manage cookbook dependencies

## How to publish artifacts to Chef server
You can publish artifacts to the Chef Server via the knife commands

### Upload a cookbook
```
knife cookbook upload --all
knife cookbook upload ax_SQLServer
```
### Upload a role
```
knife role from file chef-repo\roles\myrole.rb
```


## What Berkshelf is
Berkshelf is manages where Chef Server will go to download cookbooks, by default it will go to the public supermarket, but if needed you update the file to point it a private supermarket


## If the Chef Automate workflow feature can push artifacts to things other than a Chef server or Supermarket
You can push to nodes, github, supermarkets (private, public, multilple at the same time)


## How to manage cookbook dependencies
Cookbook dependencies are defined in the metadata.rb and in the recipe that usese the dependency. You can update the Berksfile to show where to download them from.


[Return to ](README.md)</br>
[Return to home](../README.md)
