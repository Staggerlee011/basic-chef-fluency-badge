# Push vs Pull

> Candidates should understand:
> - The difference between push and pull models
> - The benefits of a pull model
> - When a push model is appropriate
> - What firewall rules need to be enabled for Chef client
> - The Chef client converge intervals and how to invoke immediate updates


## The difference between push and pull models
### Push 
You push a single DSC to a node. 

## Pull 
You regulerally pull from a server the DSC, which will run in chef a test and repair process


## The benefits of a pull model
The benfit of a pull model is that the DSC is regularly checked and repaired if changed. ensuring that the DSC is accurate

## When a push model is appropriate
You might want to use the push model for single installs that are then snowflaked

## What firewall rules need to be enabled for Chef client
Port | Service Name, Description |	External
--- | --- | ---
4321 | bookshelf </br> The bookshelf service is an Amazon Simple Storage Service (S3)-compatible service that is used to store cookbooks, including all of the files—recipes, templates, and so on—that are associated with each cookbook. | no
80, 443, 9683 | nginx </br> The nginx service is used to manage traffic to the Chef server, including virtual hosts for internal and external API request/response routing, external add-on request routing, and routing between front- and back-end components. </br> Note Port 9683 is used to internally load balance the oc_bifrost service. | yes
9463 | oc_bifrost </br> The oc_bifrost service ensures that every request to view or manage objects stored on the Chef server is authorized. |
9090 | oc-id  </br> The oc-id service enables OAuth 2.0 authentication to the Chef server by external applications, including Chef Supermarket and Chef Analytics. OAuth 2.0 uses token-based authentication, where external applications use tokens that are issued by the oc-id provider. No special credentials—webui_priv.pem or privileged keys—are stored on the external application. |
8000 | opscode-erchef </br> The opscode-erchef service is an Erlang-based service that is used to handle Chef server API requests to the following areas within the Chef server: Cookbooks, Data bags, Environments, Nodes, Roles, Sandboxes, Search |
8983 | opscode-solr4 </br> The opscode-solr4 service is used to create the search indexes used for searching objects like nodes, data bags, and cookbooks. (This service ensures timely search results via the Chef server API; data that is used by the Chef platform is stored in PostgreSQL.) |
5432 | postgresql </br> The postgresql service is used to store node, object, and user data. |
5672 | rabbitmq </br> The rabbitmq service is used to provide the message queue that is used by the Chef server to get search data to Apache Solr so that it can be indexed for search. When Chef Analytics is configured, the rabbitmq service is also used to send data from the Chef server to the Chef Analytics server. |
16379 | redis_lb </br> Key-value store used in conjunction with Nginx to route requests and populate request data used by the Chef server. |

https://docs.chef.io/server_firewalls_and_ports.html

## The Chef client converge intervals and how to invoke immediate updates
The chef client runs a converge by default every 1800 seconds (30 Mins).  This can be updated via either:
- Using the Chef-Client cookbook 
  - https://supermarket.chef.io/cookbooks/chef-client 
  - update: `node["chef_client"]["interval"]`
- Update the client.rb file on the node
  - https://docs.chef.io/config_rb_client.html
  - Set the interval setting
    - ` interval </br> The frequency (in seconds) at which the chef-client runs. Default value: 1800. `
 

 

[Return to Design Philosophy](README.md)</br>
[Return to Home](../README.md)
