# Roles

> Candidates should understand:
> - What roles are
> - How a role ensures code consistency across nodes
> - Where roles can be stored
> - How roles are defined
> - What the components of a role are
> - Roles vs recipes vs run_lists
> - How to name roles
> - How to apply roles to nodes
> - How to edit roles

## What roles are
Describes a custom run_list. So you could set say a "Web" Role, which would include a run_list with ad_join, install_iis, config_iis. 
By using a role instead of a run_list we are able to edit all the webservers together. Where as a run_list is specific to a node.


## How a role ensures code consistency across nodes
If you were defining nodes by run_lists it is possible that you could make a manual mistake and not update them all correctly. by using a role. 1 update to a role will update all nodes using the role.


## Where roles can be stored
Roles are stored in the repo `Chef-Repo\Roles`


## How roles are defined
Roles are defined by either JSON or Ruby DSL. 
## What the components of a role are
## Roles vs recipes vs run_lists

### recipes
a set of resources that are related to each other

### run_lists 
provides a list of recipes to run in order. run_lists are specific to each node. Where as a role can be applied across many.

## How to name roles
Roles are named within the .rb or .json file (**NOTE the name of the file is not relevant to the name of the role!**) using the name attribute

example: Create a Role called SuperRunList
A file called mynewrole.json is created in `Chef-Repo\Roles`
```
{
    "name": "SuperRunList",
    "run_list": [
    ]
}
```

for a rb file
```
name 'Load-lanacer'
description 'role for proxy servers
run_list 'recipe[myhaproxy]','recipe[configproxy::specificRecipe]'
```


## How to apply roles to nodes
To apply a role to node you can either use Chef-Manage / Chef Automate or via the knife command. 

Example updating the node Web1 to use the Web role
```
knife node run_list set <node> "role[myrole]"
```

## How to edit roles


## Links
[Chef Docs - Role](https://docs.chef.io/roles.html)
[My Gist on Knife commands for Roles](https://gist.github.com/Staggerlee011/5cd3a98d49149850cb052d89afffacd0)

[Return to Chef basic terminiology](README.md)
[Return Home](../README.md)
