# Search

> Candidates should understand:
> - What search is
> - How to search for node information						
> - What and how many search indexes Chef server maintains
> - What	a	databag is						
> - How to use search for dynamic orchestration					
> - How to invoke a search from the command line

## What search is
Search is a full text indexing system to read and analyis logs


## How to search for node information						
```
knife search node 'name:prd*'
```
```
knife search node 'platform:windows*'
```
```
knife search node 'environment:production*'
```


## What and how many search indexes Chef server maintains
There a several indexes built for Chef Searching

Search Index Name | Description
--- | ---
Client | API client
DATA_BAG_NAME | A data bag is a global variable that is stored as JSON data and is accessible from a Chef server. The name of the search index is the name of the data bag. For example, if the name of the data bag was “admins” then a corresponding search query might look something like search(:admins, "*:*").
Environment | An environment is a way to map an organization’s real-life workflow to what can be configured and managed when using Chef server.
Node | A node is any server or virtual server that is configured to be maintained by a chef-client.
Role | A role is a way to define certain patterns and processes that exist across nodes in an organization as belonging to a single job function.

https://docs.chef.io/chef_search.html


## What	a	databag is						
Is a global variable. It can be used to store things like login details. By default data bags are not encrypted but can be using

https://docs.chef.io/data_bags.html


## How to use search for dynamic orchestration					


Example of running code only if the OS is max
```
cookbook_file "/etc/nginx/nginx.conf" do
  source "nginx.conf"
  not_if platform_family?("mac_os_x")
end
```

Example of using If 
```
if node['platform'] == 'ubuntu'
  # do ubuntu things
end
```

Example of case 
```
case node['platform']
when 'debian', 'ubuntu'
  # do debian/ubuntu things
when 'redhat', 'centos', 'fedora'
  # do redhat/centos/fedora things
end
```


## How to invoke a search from the command line
```
knife search node 'name:prd*'
```


## Links
[Chef Docs](https://docs.chef.io/chef_search.html)

[Return to Chef Basic Terminology](README.md)
[Return Home](../README.md)
