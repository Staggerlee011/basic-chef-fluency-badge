# Recommended Workflows

> Candidates should understand:
> - What wrapper cookbooks are
> - How to use source control, e.g. GitHub
> - How to use the TDD approach

## What wrapper cookbooks are
A wrapper cookbook is used when you are using cookbooks from the supermaket. It is suggested that you dont edit the supermarket cookbook to fit your needs, but create a new cookbook with a dependcy on the supermarket cookbook. you can then make changes in your cookbook to edit the behaviour of the orginal without forking the source code.


## How to use source control, e.g. GitHub
It is best practise to keep your Chef code in source code (Github, Gitlab, BitBucket, VSTS etc). This is used as your source of truth and the chef-server as your artifact repository. You can even use a single repository for Chef or create a repo per cookbook. If you wish to use a single source. you can create the Chef-Repo using the command 
```
Chef generate repo chef-repo
```


## How to use the TDD approach
TDD is the approach of creating a test that will fail. then writting just enough code to make the test pass. The repeating the process to build out your application. 


[Return to Design Philosophy](README.md)</br>
[Return to Home](../README.md)



