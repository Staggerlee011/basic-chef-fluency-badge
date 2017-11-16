# Chef Client

> Candidates should understand:
> - What the Chef client is
> - The function of Chef client vs the function of Chef server
> - What 'why-run' is						
> - How to use '--local-mode'						
> - How the Chef client and the Chef server communicate
> - The Chef client configuration	

## What the Chef client is
An agent (daemon) installed on every node allowing the Chef Server to talk to the node. THe client performs all opperations on a node by downloading configuation tasks and run lists from a Chef Server.

A Chef Client can run cookbooks without the use of a Chef Server via Chef-Zero.

The Chef-Client includes:
- Chef Zero (A lightweight in memory version of Chef Server)
- client.rb (A ruby file containing credentials for API calls to the Chef Server)
- Ohai (A tool used to collect system data (OS, CPU, Memory, Disk etc. It is run every time that a Chef Run is to gather information for the cookbooks)


## The function of Chef client vs the function of Chef server
The Chef Client runs on the nodes and takes actions from the Chef Server. The Chef Server hosts the cookbooks/environments/roles etc for central management


## What 'why-run' is						
Is similar to Powershell `-WhatIf` in that it will show what would happen without actually changing anything


## How to use '--local-mode'						
Allows you use cookbooks instead of downloading them from the Chef Server. Local Mode relises on Chef-Zero (lightweight Chef Server that runs in memory)

This is a handy tool for testing deployment issues as when a runlist is sent to a node it downloads the cookbooks. Allowing you to re-run and troubleshoot issues on the node instead from Chef Server.


## How the Chef client and the Chef server communicate
Clients speak to the Chef server via API calls. The Chef server only replies to trusted users using public/private keys. THe client uses poer 443 or 80 (https/http)


## The Chef client configuration	

The Chef client is configured via the client.rb file.
- Linux path `/etc/chef/client.rb`
- Windows path ` C:\chef\client.rb`


## Links 
[Chef Docs - Chef-Client](https://docs.chef.io/ctl_chef_client.html)
[Chef Client Overview](https://docs.chef.io/chef_client_overview.html)

[Return to Chef Basic Terminology](README.md)

[Return Home](../README.md)

