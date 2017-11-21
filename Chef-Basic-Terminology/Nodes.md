# Nodes

> Candidates	should	understand:
> - What a node is						
> - What a node object is						
> - How a node object is stored on Chef server	
> - How to manage nodes
> - How to query nodes						
> - How to name nodes	

## What a node is						
Is a machine under management of Chef (Has the Chef client installed) This can be a server (physcial or virtual), container or network device. 

A node will contain the Chef-Client and Ohai 


## What a node object is						
A node object is the nodes run-list and the attributes assigned to the node. All the values can be edited for a specific node.

## How a node object is stored on Chef server	
The node object is stored as a JSON file on the Chef Server. It is updated after every Client-Run command to a node.


## How to manage nodes
- You can manage a node via Chef Manage/Automate (Web interface)  
- Knife commands 
- Chef-Client


## How to query nodes						
You can query a node via Knife commands

```
knife node list 
```
will list all nodes connected to the Chef Server


## How to name nodes	
A node can be named anything that follows the expressions `/^[\-[:alnum:]_:.]+$/` but must be unque within the Chef Server.


## Nodes
[Chef Docs - Manage nodes](https://docs.chef.io/server_manage_nodes.html)</b>
[Chef Docs - About nodes](https://docs.chef.io/nodes.html)</b>
[Chef Docs - Knife node](https://docs.chef.io/knife_node.html)

[Return to Chef Basic Terminology](README.md)</b>
[Return to Home](../README.md)

