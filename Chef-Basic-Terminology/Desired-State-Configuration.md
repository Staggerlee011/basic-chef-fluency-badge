# Desired State Configuration

> Candidates should understand:
>  - The imperative	vs the declarative approach to configuration management	
>  - The push vs the pull approach	
>  - What Windows DSC is						
>  - What happens if you remove a resource from a recipe	

## The imperative vs the declarative approach to configuration management	

### Declarative
examples would be TSQL and DSC. You do not define how to get to the result only the expected outcome

### Imerative
examples would be Chef recipes, where you build out the steps to get to desired outcome


## The push vs the pull approach	

### push
When doing a push approach, you are doing a single definition of what you wish to deploy and applying it against the server.

### pull
A standard DSC Pull approach would require a DSC Server. this would host the config files and regularly run test-and-repair. When using Chef with DSC the Chef server acts as the pull server.

## What Windows DSC is						
A declarative configuration management platform in PowerShell (v4+)

Note for using DSC in Chef it is suggested to create a cookbook to set the LCM to ApplyOnly instead of the defauly ApplyAndMonitor. This will stop the LCM running checks and duplicating what Chef is doing.


## What happens if you remove a resource from a recipe
If you remove a resource from a recipe after it has been run on a node. no changes will be made on the next run (Ie it will not remove that change)


## Links
[MS docs - DSC Overview](https://docs.microsoft.com/en-us/powershell/dsc/overview)</b>
[LCM ApplyOnly Issue](https://github.com/chef/chef/issues/2470)


[Return to Chef Basic Terminology](README.md)</b>
[Return to Home](../README.md)


