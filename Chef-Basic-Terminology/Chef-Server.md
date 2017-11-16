# Chef Server

> Candidates should understand:
> - How the Chef server acts as an artifact repository						
> - How the Chef server acts as an index of node data						
> - Chef solo vs Chef server	
> - Chef server's distributed architecture	
> - Scalability	


## How the Chef server acts as an artifact repository						
The Chef Server stores the below artifacts 
- Roles
- Cookbooks
- Environments
- DataBag
- Nodes
- Ohai Data


## How the Chef server acts as an index of node data						
Chef Server is made of several components 
- Search (Collection of Indexes to query for information related to nodes)
- Manage (web console to manage Nodes, Cookbooks, Roles etc
- Data Bag (Password vault)
- Policy (Maps roles, environments and cookbook versions together)

The Search component of Chef Server is based on following indexes
- client (api client)
- DATA_BAG_NAME (data bag details)
- environment (environment details)
- node (list of nodes)
- role (role information)

You can run searches via the knife command `knife search` More details below:
[Chef Search](https://docs.chef.io/chef_search.html)


## Chef solo vs Chef server	
Chef Solo is a command tool that executes the Chef-Client in a way that does not require a Chef Server allowing you to run cookbooks locally. 

Chef Solo is part of the Chef-Client install 


## Chef server's distributed architecture	
As the Chef Server is primarly a artifact repo (storing cookbooks and policies etc) It is the Chef-Client that does all the heavy lifting when actually running the cookbooks. 

> This scalable approach distributes the configuration effort throughout the organization.
https://docs.chef.io/chef_overview.html


## Scalability
> The Chef server itself is highly scalable. A single virtual machine running the Chef server can handle requests for many thousands of nodes. As the scale increases, it’s a straightforward process to expand into a tiered front-end, back-end architecture with horizontally scaled front-ends to relieve pressure on system bottlenecks.
> That said, it’s best to isolate failure domains with their own Chef server, rather than trying to run every node in an infrastructure from a single central, monolithic Chef server instance/cluster.
> For instance, if there are West coast and East coast data centers, it is best to have one Chef server instance in each datacenter. Deploys to each Chef server can be synchronized upstream by CI software. The primary limiting bottleneck for Chef server installations is almost always input/output operations per second (IOPS) performance for the database filesystem.
https://docs.chef.io/server_components.html

[Chef Summit 2014 - Chef Server Scaling](https://github.com/chef/chef-summit-2014/wiki/Chef-Server-Scaling)


## Links 
[An Overview of Chef](https://docs.chef.io/chef_overview.html)
[Chef Server Components](https://docs.chef.io/server_components.html)


[Return to Chef Basic Terminology](README.md)
[Return to Home](../README.md)
