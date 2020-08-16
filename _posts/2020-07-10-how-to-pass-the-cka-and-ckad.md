---
layout: post
title: How to Pass the CKA/CKAD with Ease
date: 2020-07-10
description: 
img: cka-cert.png
thumbnail: cka-logo.png #cka-certified-kubernetes-administrator.png
tags: [Work, Learning] # add tag
---


### My Background
With the Certified Kubernetes Administrator / Certified Kubernetes Application Developer certifications growing in popularity, I would like to give some insight on my experiences with taking the certification exams.  


For a little background on myself, I am currently still a college student at UVA, have taken some Udemy/LinkedIn Learning courses related to Docker in the past, and have had little to no experience with container orchestration in the past (tad bit of Docker Swarm).  Even with limited experience in the field, I found that the two exams were relatively straightforward, and with the right amount of prep work, it is very achievable to obtain both certifications in less than a month.

### Where to Start

Navigate to this page on the CNCF website and read through it once before starting: [CNCF website](https://www.cncf.io/certification/cka/).
It's important to look over what is expected during the exam, and the site highlights the major topics covered in it.  
In regards to how I prepared, I **STRONGLY** recommend fully completing the following Udemy courses as preparation for the exams: <a href="https://www.udemy.com/course/certified-kubernetes-administrator-with-practice-tests" target="_blank">CKA</a> and <a href="https://www.udemy.com/course/certified-kubernetes-application-developer" target="_blank">CKAD</a>. Mumshad Mannambeth does a phenomenal job with teaching what is needed in order to pass both exams, and the KodeKloud Training practice exams/labs are very effective in getting the practice you will need to use Kubernetes in a production-level environment.  In addition, the CKA course has a module on "Kubernetes the Hard Way", to get an in-depth understanding of how the services work together. It is not covered on the exam, as the exam will be using kubeadm, but it will help you strenghten the concepts.

### Time Commitment

The time needed to prepare for the exam will vary case by case, but I believe that once you have completed the respective course for the certification, are able to complete the labs, and most importantly complete the practice exams with plenty of time left (while scoring 100%), you will be prepared enough to pass the certification. The two tests are very different compared to other certification exams, so spending a great deal of time getting comfortable with quickly getting the information you need (via kubectl, etcdctl, etc.) is a must.  

### General Tips
- **Make use of bookmarks**: You are allowed full access to the <a href="https://kubernetes.io/docs" target="_blank">Kubernetes Documentation</a> (See CNCF guidelines for the exams), so use it! Being able to navigate the site quickly can save you time, as you can copy/paste sample yaml files or commands (and see proper usage of a command) directly into the test and modify them to your own discretion.
- **Time Management**: In order to manage your time effectively, I believe that getting familiar with the Kubernetes documentation and spending a lot of time practicing the concepts in the Udemy courses is needed. I also recommend flagging questions that you are either unsure about and cannot complete correctly (the first time around), so that you don't get stuck on a single question. Lastly, be careful with when you SSH into particular nodes. You'll need to do an initial exit for when you are in su mode, and another to get out of the node. If you do it a third time, you will lose connection and the environment will reload (takes 5-10 minutes). Make sure to pay attention when you use exit.
- **Kubernetes Tasks List**: On the Kubernetes documentation page, navigate to the Tasks page. If you need extra practice in a specific field, find the related task on the Tasks page and complete it for extra practice.