# Test Kitchen

> Candidates should understand:
> - The Test Kitchen value proposition
> - What TDD is
> - The platforms supported by Test Kitchen
> - How to include Test Kitchen in a pipeline
> - Basic `kitchen` commands
> - Basic `kitchen` configuration

## The Test Kitchen value proposition
Test-Kitchen allows you run TDD against your Chef cookbooks. It will bring up a test server, run your cookbooks/recipes against it, run tests then either destory the server or let you login so you can check the config or troubleshoot the issue. Test-Kitchen connects to most if not all major providers (AWS, Azure etc) as well as local clients like VirtualBox and Vagrant.


## What TDD is
TDD is the idea of creating tests before you create code. If you want to create a windows cookbook to install IIS. you would start by creating a test to see if IIS is installed on the machine. This would fail. You would then write the code to install IIS. and try running the test again (which should pass). 


## The platforms supported by Test Kitchen
Driver | Plugin	Description
--- | ---
kitchen-all |	A driver for everything, or “all the drivers in a single Ruby gem”.
kitchen-bluebox |	A driver for Blue Box.
kitchen-cloudstack |	A driver for CloudStack.
kitchen-digitalocean |	A driver for DigitalOcean.
kitchen-docker |	A driver for Docker.
kitchen-dsc |	A driver for Windows PowerShell Desired State Configuration (DSC).
kitchen-ec2 |	A driver for Amazon EC2.
kitchen-fog |	A driver for Fog, a Ruby gem for interacting with various cloud providers.
kitchen-google |	A driver for Google Compute Engine.
kitchen-hyperv |	A driver for Hyper-V Server.
kitchen-joyent |	A driver for Joyent.
kitchen-linode |	A driver for Linode.
kitchen-opennebula |	A driver for OpenNebula.
kitchen-openstack |	A driver for OpenStack.
kitchen-pester |	A driver for Pester, a testing framework for Microsoft Windows.
kitchen-rackspace |	A driver for Rackspace.
kitchen-terraform |	A driver for Terraform.
kitchen-vagrant	| A driver for Vagrant. The default driver packaged with the Chef development kit.

https://docs.chef.io/kitchen.html


## How to include Test Kitchen in a pipeline


## Basic `kitchen` commands
### list kitchen test state
```kitchen list```

### creates vm based on kitchen.yml
```kitchen create```

### applies cookbook to vm
```kitchen converge```

### kitchen verify runs tests from folder: 
```kitchen verify```

### test (destory -> create -> converge -> verify -> destory)
```kitchen test```

### rdp - if not specificing in driver_config then it uses azure/P2ssw0rd for login/password
```kitchen login```

### example calling the vm 
```
kitchen exec -c '(Invoke-WebRequest -UseBasicParsing localhost).Content'
kitchen exec -c 'Get-Acl c:\inetpub\wwwroot\Default.htm | Format-List'
kitchen exec -c 'Get-DscLocalConfigurationManager | select -ExpandProperty "ConfigurationMode"'
```

## Basic `kitchen` configuration
To connect Test-Kitchen to your provider you will to configure the kitchen.yml file and download/configure your authentication. 

To complete the steps for Azure follow the steps outlined in this post: https://learn.chef.io/modules/local-development#/


## Links
[Chef Docs - Test Kitchen](https://docs.chef.io/kitchen.html)</b>
[learn.chef - local development and testing](https://learn.chef.io/tracks/local-development-and-testing#/)

[Return to Chef Basic Terminology](README.md)</b>
[Return to Home](../README.md)
