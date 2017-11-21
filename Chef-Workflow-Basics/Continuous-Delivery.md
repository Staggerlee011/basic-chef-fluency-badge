# Continuous Delivery

> Candidates should understand:
> - What continuous delivery (CD) is
> - What role Chef plays in CD
> - When to run tests
> - Why automated configuration management is critical to CD
> - Why CD is *more* secure than manual processes

## What continuous delivery (CD) is
CD is the process of being able to deploy a artifact when needed. This is different to Continous Deployment which will deploy the changes when the artifact is made.


## What role Chef plays in CD
If you have purchased Chef Automate you can build you CI/CD pipeline using Chef Workflow. If you are using the open source tools. You can still create a pipeline by using Test-Kitchen and Inspec.


## When to run tests
You should run tests during development and after any changes.


## Why automated configuration management is critical to CD
the automed process allows for CD to be created by pipelines. 


## Why CD is *more* secure than manual processes
CD is *more* secure due to the fact that no user needs to login or interface with the node. The code will be deployed via the chef-client ensuring tha test and repair process will result in the same outcome each time.



[Return to ](README.md)</br>
[Return to home](../README.md)

