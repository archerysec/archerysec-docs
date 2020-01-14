---
title: Burp Suite Scanner
category: Scanners
chapter: 3
order: 2
---

Burp Suite is an integrated platform for performing security testing of web applications. It is designed to support the methodology of a hands-on tester, and gives you complete control over the actions that it performs, and deep analysis of the results. Burp contains several tools that work together to carry out virtually any task you will encounter in your testing. It can automate all kinds of tasks in customizable ways, and lets you combine manual and automated techniques to make your testing faster, more reliable and more fun.

 ![ZAP Scanner](/images/screenshots/burp_suite.png)

 Archery has in built plugin for Burp Suite Scanner and you can utilize to perform automated way scanning on your web applications. You need to have Burp Suite Professional version.

## Enable Burp API

Please follow below link to enable Burp API: 

[https://portswigger.net/blog/burps-new-rest-api](https://portswigger.net/blog/burps-new-rest-api)

#### Setting in Archery

- Go to Setting Page
- Edit Burp Setting
- Provide API Key
- Provide Burp API Host as `127.0.0.1`
- And Burp API Port as `8090`

Now navigate to Domain scan page and launch the scans using Burp scanner.

