# Environments

> Candidates should understand:
> - The purpose of environments
> - How to use environments to manage cookbook release cycles
> - How to use environments to constrain cookbooks
> - How to put nodes into an environment

## How to use environments to manage cookbook release cycles
Environments are way to create workflows for updating / bug fixing cookbooks. You start with a default environment for all nodes called _default. But can create as many as you like. 

A simple example of using environments is:
- create a development and production environments setting everything to production by default. 
- Set all cookbooks to deploy the specific version they are on
- When developing a new verison ensure you update the version (Thus making sure it can be deployed during your development
- When you wish to try the deployment. Set a sever to development and it will deploy the latest verions which you can then confirm works as intended.

## How to use environments to constrain cookbooks
You can do this manually in Chef Manage making the change on the cookbook

![cookbookenvironmentversionconstraint](https://github.com/Staggerlee011/basic-chef-fluency-badge/blob/master/img/CookbookEnvironmentVersionConstraint.png)

Or you can do it via code: 

????


## How to put nodes into an environment
You can do this manuall in CheF Manage going into the Nodes tab, Selecting the node you wish to change and switching the environment.

![cookbookenvironmentversionconstraint](https://github.com/Staggerlee011/basic-chef-fluency-badge/blob/master/img/ChangeNodeEnvironment.PNG)

Or you can do it via code:


## Links
[Chef Docs - Environments](https://docs.chef.io/environments.html)</b>
[Chef docs - Manage Envrionments](https://docs.chef.io/server_manage_environments.html)

[Return to Chef Basic Terminology](README.md)</b>
[Return to Home](../README.md)


