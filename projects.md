---
layout: page
title: Projects
permalink: /projects/
description: Descriptions of the projects I've worked on.
---

I've worked on a few projects. If I thought it turned out well, I've written about it here. Otherwise, see my github.

___

## [cufcq.com](http://cufcq.com)

I worked with my friend [Sam](untra.io) to take on the university and build a website to summarize CU's teacher survey data. Project highlights:

  - Built on Rails.
  - 23,000+ users and 224,000+ page views.
  - Zero 500 (Internal Server) errors. Not bad for a project started sophomore year.

Find the source code [here](https://github.com/antsankov/cufcq).

___

## [BroCI](https://github.com/antsankov/BroCI)

During my senior year, I built a continuous integration system from scratch for the Bro intrusion detection system (IDS). This allowed security administrators to virtually test and validate scripts before they deployed them to their Bro cluster.

  - Published a [paper][broci] along the way. Was invited to present at the NFV conference in San Jose and at an ACM conference in New Orleans.
  - Created a test platform and continuous integration system for a security appliance.
  - Designed and built a pretty dashboard to go along with it.

[broci]: https://www.academia.edu/26635068/Taking_the_Surprise_out_of_Changes_to_a_Bro_Setup

___

## [Mr.Roadboto](http://m.me/roadboto)

A low-bandwidth and easy to use Facebook chat bot that serves Colorado's Department of Transportation (CDOT) alerts for I70 road-closures affecting major ski resorts. You can read about the motivation here. This was entirely built using AWS Lambdas for chat and information scraping, and a Redis cache for persistence. [here](https://medium.com/@antsankov/domo-arigato-mr-roadboto-pt-1-introducing-the-problem-b0d44e384dc).

  - Discovered and [shared the dangers](https://hackernoon.com/dealing-with-an-aws-billing-surprise-beware-the-defaults-d8a95f6635a2) of over-provisioning Lambda functions on AWS.
  - Learned how to wrangle an XML api out of a government agency.
  - Experienced the joys of manually mapping satellite coordinates to road junctions using GIS.

Find the source code [here](https://github.com/antsankov/MrRoadboto)

___

## [PhishMonger](https://github.com/untra/phishmonger)

I worked with some friends to create an incentivized phishing platform during the 2015 Money2020 Hackathon. The pitch: companies would phish their employees, and run a system of corporate prizes that would automatically donate to a charity if the employee reported the link, and deduct money depending on how much information they gave.

  - All made over the course of 24 crazy hours in Las Vegas.
  - Building a good looking and effective phishing page is *stupid* easy.
  - For the reward schema, designed and built an object-oriented Python wrapper around an API only accessible by Bash.
