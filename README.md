# Tomcat on CentOS

The [Apache Tomcat®](http://tomcat.apache.org/) software is an open source implementation of the Java Servlet, JavaServer Pages, Java Expression Language and Java WebSocket technologies. The Java Servlet, JavaServer Pages, Java Expression Language and Java WebSocket specifications are developed under the Java Community Process.

## Objectives

The goal is to transform the installation instructions into one or more Chef recipes that will install and initialize the application.

After successfully completing this workshop, you will be able to:

* Build something in Chef with very little guidance
* Write custom Chef recipes.
* Use the [Chef Documentation](http://docs.opscode.com) to identify and use resources that will help you model the desired state of your infrastructure.

## Pre-requisites

Before beginning you will need:

* A virtual machine or server running CentOS 6.7 or similar
* Some experience using Chef such as:
  * completing the exercises on [Learn Chef](http://learn.chef.io)
  * completing a Chef Essentials workshop
  * real-world experience working with Chef
* Chef DK or chef-client installed
* Docker installed and configured along with the kitchen-docker gem
* A text editor

## Completion Criteria

You'll know this project is complete when:

* Your tests report a successful response from your Tomcat site
* You can run chef-client multiple times without failures

## Next steps

You can take expand on this project a number of ways including:

* Testing
  * Use [Test Kitchen](http://kitchen.ci) to validate your chef-client runs
  * Add static code analysis using [Rubocop](https://github.com/bbatsov/rubocop) and [Food Critic](foodcritic.io)
  * Add [ChefSpec](http://sethvargo.github.io/chefspec/) tests
  * Add [Inspec](http://inspec.io/) tests
  * Add a continuous integration server, such as Jenkins

* Refactoring Recipes

Typically recipes perform installation and configuration for a single application or a service of an application. Separate your single cookbook recipe into different recipes that focus on each of the different applications (e.g. installing ruby, installing apache, cloning the repo, installing dependencies, configuring/enabling the thin service).

Use the [include_recipe](https://docs.getchef.com/essentials_cookbook_recipes.html#include-recipes) directive to ensure you load your dependencies.

* Cookbook Extraction

Cookbooks are best when they map 1:1 to a piece of software. The cookbook created here contains so much awesomeness across so many pieces of software. Separate the recipes in your single cookbook into multiple cookbooks (e.g. Apt-Get, Apache, Ruby, Git, Bundler)

* Replace with [Community Cookbooks](http://supermarket.getchef.com)

The community has created cookbooks that accomplish similar goals. Select a group of resources, recipe, or cookbook and replace it with the equivalent community cookbook.

* [Custom Resources](https://docs.chef.io/custom_resources.html)

Within your cookbook several resources that act in concert together can be grouped together as a recipe. Sometimes it makes sense to use a series of resources as a template. Custom Resources  grant you that ability.

Update your current resources, recipes, and cookbooks to implement a custom resource where it feels like you may want to use that same series of resources again with a different set of parameters.

* Multi-OS support

The installation instructions were defined for a CentOS Operating System (OS). Attempt a deployment on a node with a different OS. Update the resources, recipes, and cookbooks so that you can deploy on Ubuntu? Redhat? Amazon?
