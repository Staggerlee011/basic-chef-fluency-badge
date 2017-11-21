# Run-List

> Candidates should understand:
> - What a run_list is
> - What nested run_lists are
> - Where a run_list is stored
> - What does a run_list consist of
> - How to look up run_lists
> - How to set and change run_lists

## What a run_list is
A run_list is a set of a recipes that are run in order. A run_list can also use a role 


## What nested run_lists are
A nested run_list is a run_list containing a role (As a role contains multiple recipes).

## Where a run_list is stored
The run_list is stored in the Chef Server and on nodes (In the client.rb file)

## What does a run_list consist of
A run_list consists of either an array of recipes ie:
```
run_list: "recipe[basicconfig::join_ad]", "recipe[web::install_iis]", "recipe[website1]"
```

If a run_list uses a role it will look like:
```
run_list: "role[beats-client]
```


## How to look up run_lists
You can look up run_lists using the knife node show
```
c:\GIT\internal_infra\chef-repo\roles>knife node show prd-los-int02  -r
prd-int02:
  run_list: role[beats-client]
```

## How to set and change run_lists
You can set or update a run_list in Chef Manage/Automate or via the `knife node` commands

To set a run_list you can use 
```
knife node run_list <NODE> 'recipe[iis]'
```

To update a run_list above and add the recipe[basicconfig::join_ad] recipe BEFORE recipe[iis]
```
knife node run_list add <NODE> recipe[basicconfig::join_ad] -b recipe[iis]
```
this will result in a run_list like: 
```
c:\GIT\internal_infra\chef-repo\roles>knife node show prd-los-int02  -r
prd-int02:
  run_list: recipe[basicconfig::join_ad], recipe[iis]
```

To update the same run_list again and add a recipe AFTER recipe[iis]
```
knife node run_list add <NODE> recipe[website1::config] -a recipe[iis]
```
this will result in a run_list like: 
```
c:\GIT\internal_infra\chef-repo\roles>knife node show prd-los-int02  -r
prd-int02:
  run_list: recipe[basicconfig::join_ad], recipe[iis], recipe[website1::config]
```

To Delete a run_list item:
```
knife node run_list remove <NODE> recipe[website1::config] 
```
this will result in a run_list like: 
```
c:\GIT\internal_infra\chef-repo\roles>knife node show prd-los-int02  -r
prd-int02:
  run_list: recipe[basicconfig::join_ad], recipe[iis]
```


## Links
[Chef Docs - Run-Lists](https://docs.chef.io/run_lists.html)</b>

[Return to Chef Basic Terminology](README.md)</b>
[Return to Home](../README.md)
