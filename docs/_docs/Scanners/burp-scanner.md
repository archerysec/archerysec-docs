---
title: Burp Suite Scanner
category: Scanners
chapter: 3
order: 2
---

Burp Suite is an integrated platform for performing security testing of web applications. It is designed to support the methodology of a hands-on tester, and gives you complete control over the actions that it performs, and deep analysis of the results. Burp contains several tools that work together to carry out virtually any task you will encounter in your testing. It can automate all kinds of tasks in customizable ways, and lets you combine manual and automated techniques to make your testing faster, more reliable and more fun.

 ![ZAP Scanner](/images/screenshots/burp_suite.png)

 Archery has in built plugin for Burp Suite Scanner and you can utilize to perform automated way scanning on your web applications. You need to have Burp Suite Professional version.

## Burp Suite Setup with Archery

Archery using burp scanner REST API enabled by [vmware/burp-rest-api Github project](https://github.com/vmware/burp-rest-api)

Build & Run burp-rest-api

- Download or Clone [vmware/burp-rest-api Github project](https://github.com/vmware/burp-rest-api)
- [Download](https://portswigger.net/burp) the Professional edition of Burp Suite.
- Create a lib folder under the [vmware/burp-rest-api Github project](https://github.com/vmware/burp-rest-api) project directory and place the Burp Suite JAR file into it.
- The project can be run either by running the Gradle Spring `bootRun` command or by directly launching the JAR created from building the project:

```bash
# build the jar (note that testing phase will fail if you provide free edition jar in ./lib)
gradlew clean build

# and run it without headless mode
java -jar burp-rest-api-1.0.2.jar --headless.mode=false

```

Above commands we are running to build burp rest API and start the Burp Suite. Burp REST API by default running on localhost and port 8090.

To modify the server port on which the API is accessible, use one of the following commands:

```bash

# With the executable JAR:

java -jar burp-rest-api-1.0.0.jar --server.port=8081

# OR

java -jar burp-rest-api-1.0.0.jar --port=8081

```

Note - Make sure your burp scanner should be resume and running

 ![burp-scan-run](/images/screenshots/burp_scan_run.png)

Navigate `http://127.0.0.1:8090/swagger-ui.html#/` to verify Burp REST API are accessible.

#### Setting in Archery
<br>
![burp-setting](/images/screenshots/edit_burp.png)

- Go to Setting Page
- Edit Burp Setting
- Provide Burp API Host as `127.0.0.1`
- And Burp API Port as `8090`

Now navigate to Domain scan page and launch the scans using Burp scanner.

