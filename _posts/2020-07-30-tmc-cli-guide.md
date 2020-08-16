---
layout: post
title: Tanzu Mission Control CLI Guide
date: 2020-07-30
description: A little tutorial on using the TMC CLI to create clusters, sign in, etc.
img: vm-tanzu.png
thumbnail: tmc-cli-cg.png
tags: [Work, Learning] # add tag
---

Hello everyone, in this post, I will be going over some of the CLI capabilities for Tanzu Mission Control.

To begin, in order to get the CLI onto your system you will need to navigate to Tanzu Mission Control and click on the Automation Center tab.  From there, you can download the CLI onto your local system.  You will then want to follow the steps to initialize the CLI as defined in the screenshot below.  This will require you to create an api-token under your user settings.  

![tmc-cli-download]({{site.baseurl}}/assets/img/tmc-cli-download.png)

Once you are logged in by running the command `tmc login` in your terminal, you can verify which TMC contexts you have on your system, as well as your current context with the following commands: `tmc system context list` and `tmc system context current`.  The first command lists the contexts you have logged into, and the second one shows you which one is your current one.

![tmc-system-context-list]({{site.baseurl}}/assets/img/tmc-system-context-list.png)

## Creating Managed Namespaces, Clusters, Clustergroups, and Workspaces 

To create a clustergroup using the CLI, run the following command:  
`tmc clustergroup create -n <clustergroup name> -d "Insert description here"`  

![tmc-cli-cg]({{site.baseurl}}/assets/img/tmc-cli-cg.png)

As seen below, the clustergroup is visible on the TMC GUI.

![tmc-cli-cg-gui]({{site.baseurl}}/assets/img/tmc-cli-cg-gui.png)


To create a workspace, run a similar command:

`tmc workspace create --name <workspace name>`

To create a managed namespace, run the command:

`tmc cluster namespace create -c <cluster name> -n <namespace name> -k <workspace name> -d "Insert description here"`

To create a cluster, run the command:

`tmc cluster create -n <name> -c <account name credential> -s "" -g <clustergroup>`

### Wizard
The wizard makes it very easy to create a cluster or managed namespace using the CLI (note these two objects take in the most required inputs from the objects covered in this section.) As seen in the screenshot, it will go through the required inputs and show all available options for each input. 
- Using wizard for a cluster: `tmc cluster create -w`  
- Using wizard for a managed namespace: `tmc cluster namespace create -w`  

![tmc-cluster-wiz]({{site.baseurl}}/assets/img/tmc-cluster-wiz.png)

## Advanced Queries 

The TMC CLI has powerful capabilities that can help get these necessary inputs to fully automate the setup/cleanup of a multi-cluster (multi-cloud) environment.  I believe that if you have extra interest in this automation, it would be worth some time to see the output JSON values from various tmc commands (most list/get commands using TMC, with an added `-o json` to get the output returned in a JSON format). From there, you can use various jq commands to query the information that you would need to know.  A sample query can be found below, that lists all the available regions by name, and Kubernetes version available on that region.  You can also view the entirety of the json and see other important fields, such as sshKeyName, instanceType and zoneName.  

`tmc cluster options list <account name credential> -o json | jq -r '.regionalOptions[] | .regionName, .versionList[].name, ""'  `

A sample output of this query can be found in the screenshot below:

![tmc-jq-capability]({{site.baseurl}}/assets/img/tmc-jq-capability.png)

Note: If you are still new to using jq, I suggest practicing through using a site such as [jqplay.org](https://jqplay.org) to get a feel for how you can quickly get the information you need from large json files.


