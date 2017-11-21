# Products and Features

> Candidates should understand:
> - The Chef Automate value proposition
> - The Chef Automate features
> - What the workflow feature is and how it affects productivity
> - What the compliance feature is and how it affects workflow
> - What the visibility feature is and how it affects workflow
> - How a private Supermarket fits into a workflow
> - The Chef Automate open source components
> - What Visibility is
> - What Habitat is
> - What InSpec is
> - What Chef Compliance is


## The Chef Automate value proposition
Chef automate is purchased based on the number of nodes that you connect to. It is a front end wrapper for Chef-Server but adds value via expanding on:


## The Chef Automate features
  - Gives a front end tool to visualise your chef environment
  - If you run compliance checks using InSpce you have the Chef Compliance tab showing the results and managing the running of tests.
  - Workflow
  
  
## What the workflow feature is and how it affects productivity
Chef Workflows are made up of pipelines for running your cookbooks through, they can run test-kitchen and acceptance before before being released.

## What the compliance feature is and how it affects workflow
Complaince gives you a a collection of built in profiles to run (MS Windows Server, Docker, etc) As well as Security hardening profiles (Linux Security, Windows Security). This allow you to check complaince factors in your workflows with limited fuss.

## What the visibility feature is and how it affects workflow
Chef node visibility gives you the ability to visualise what a nodes health is based against either complaince checks or run_lists. 

##  How a private Supermarket fits into a workflow
By having a private supermarket you can ensure that your secure or non-internet enabled servers can access all cookbooks via updating the berksfile.

## The Chef Automate open source components
- Chef-Server
- InSpec
- Habitat

## What Visibility is
Visibility the front end tool to view the results and actions caused by chef

## What Habitat is
https://www.habitat.sh/


## What InSpec is
https://www.inspec.io/

InSpec is a unit testing framework that can be used for auditing/compliance and TDD (with Test-Kitchen). It runs on all platforms and is based in ruby. 

### Example InSpec Test for Windows
```
# Author: Christoph Hartmann
# Target OS: Windows 2012+

describe file('C:/Windows/explorer.exe') do
  it { should exist }
  it { should be_file }
end

describe user('Administrator') do
  it { should exist }
end

# look for all administrators: SID: S-1-5-21domain-500
describe users.where { uid =~ /S\-1\-5\-21\-\d+\-\d+\-\d+\-500/ } do
  it { should exist }
end

## package example
describe package('InSpec v1.19.2') do
  it { should be_installed }
  its('version') { should eq '1.19.2.1' }
end

describe windows_task('\Microsoft\Windows\AppID\PolicyConverter') do
  it { should exist }
  it { should be_disabled }
  its('logon_mode') { should eq 'Interactive/Background' }
  its('last_result') { should cmp 267011 }
  its('task_to_run') { should cmp '%Windir%\system32\appidpolicyconverter.exe' }
end
end
```
http://lollyrock.com/articles/inspec-windows/

### Example running the Test against a remote machine
```
inspec exec test.rb -t winrm://Administarator@PRD-SERVER-1 -p 'P@ssword'
```


## What Chef Compliance is
Chef Compliance is part of Chef-Automate. It gives a front end GUI to InSpec and its results. Allowing for a sinlge point to query and view results.


[Return to Describing What Chef is](README.md)</b>
[Return to Home](../README.md)
