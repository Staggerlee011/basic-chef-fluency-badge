# Resources

> Candidates should understand:
> - Idempotency/convergence - test & repair model						
> - Common resources and their actions
> - Default actions	
>   - The ':nothing'	action						
>   - The 'supports'	directive						
>   - The 'not_if' and 'only_if' directives	
> - Resource	extensibility

## Idempotency/convergence - test & repair model
Chef uses an approach called test-and-repair.<br>

In the 'test' part of test-and-repair, the resource queries the system to figure out its current state. For example, if the resource is a package that should be installed, then the resource first queries the system to see if the package is already present. For a service, it would check to see if it is already running. If the package is already installed or the service is already running, no action takes place.<br>

The 'repair' portion is where the resource takes the specified action to bring the system into the desired state. This means, for example, that it would install the package or start the service. Resources can be configured to take action only when other resources take action. For example, you would only want to download a file if you knew that the file existed on a server.<br>

https://learn.chef.io/modules/web-operations-essentials/web-operations-with-chef#/


## Common resources and their actions

## Default actions	
### The ':nothing'	action						
Define this resource block to do nothing until notified by another resource to take action. When this resource is notified, this resource block is either run immediately or it is queued up to be run at the end of the chef-client run.

```
service 'memcached' do
  action :nothing
end
```

### The 'supports'	directive						
Is a setting in the metadata.rb file to show which OS's the cookbook will run on.

```
supports 'ubuntu'
```

### The 'not_if' and 'only_if' directives	
#### not_if
Prevent a resource from executing when the condition returns `true`

Example: Install the Web-Server windows feature, if it doesnt exist already.
```
powershell_script 'Install IIS' do
  code 'Add-WindowsFeature Web-Server'
  guard_interpreter :powershell_script
  not_if "(Get-WindowsFeature -Name Web-Server).Installed"
end
```

#### only_if
Allow a resource to execute only if the condition returns `true`
```
only_if powershell_out("get-website | where-object { $_.name -eq  'My_Web_App' }").stdout.empty?
```

## Resource	extensibility


## Links
[Test and Repair](https://learn.chef.io/modules/web-operations-essentials/web-operations-with-chef#/)
[Chef docs - Resources](https://docs.chef.io/resources.html)
[]()
[]()
[]()

[Return to Chef Basic Terminiology](README.md)
[Return Home ](../README.md)
