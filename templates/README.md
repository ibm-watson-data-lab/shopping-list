To use this template, view as plain text (it contains comments), then edit as appropriate (start by deleting this line!)

<!--Put badges at the very top -->
<!-- Travis CI: change the repos (required) -->
<!-- Metrics collection: Follow the setup instructions for the appropriate client in https://github.com/IBM/metrics-collector-service  (required) -->
<!-- remove metrics badge if no metrics collection is performed --> 
[![Build Status](https://travis-ci.org/IBM/watson-banking-chatbot.svg?branch=master)](https://travis-ci.org/IBM/watson-banking-chatbot)
![IBM Cloud Deployments](https://metrics-tracker.mybluemix.net/stats/527357940ca5e1027fbf945add3b15c4/badge.svg)

<!-- fill in the blanks -->
# Create an Offline First Shopping List with [technologies]

In this code pattern, we will create an Offline First shopping list. Shopping List is an Offline First demo Progressive Web App built using [technologies]. [This app is part of a series of Offline First demo apps, each built using a different stack.](https://github.com/ibm-watson-data-lab/shopping-list).

When the reader has completed this Code Pattern, they will understand how to:

* [goal 1]
* [goal 2]
* [goal 3]
* [goal 4]

<!--Remember to dump an image in this path-->
![](doc/source/images/architecture.png)

## Flow
<!--Add new flow steps based on the architecture diagram-->
1. Step 1.
2. Step 2.
3. Step 3.
4. Step 4.
5. Step 5.

<!--Update this section-->
## Included components
Select components from [here](https://github.ibm.com/developer-journeys/journey-docs/tree/master/_content/dev#components), copy and paste the raw text for ease
* [Component](link): description
* [Component](link): description

<!--Update this section-->
## Featured technologies
Select components from [here](https://github.ibm.com/developer-journeys/journey-docs/tree/master/_content/dev#technologies), copy and paste the raw text for ease
* [Technology](link): description
* [Technology](link): description

# Steps
* [Deploy to IBM Cloud](#deploy-to-bluemix) **OR** [Run locally](#run-locally)
* [Database and replication setup](#database-and-replication-setup)

## Deploy to IBM Cloud
<!--Update the repo and tracking id-->
[![Deploy to IBM Cloud](https://metrics-tracker.mybluemix.net/stats/5c5df69e10058d49cdc1f4d2fc63ce31/button.svg)](https://bluemix.net/deploy?repository=https://github.com/ibm-watson-data-lab/shopping-list-polymer-pouchdb)

1. Press the above ``Deploy to IBM Cloud`` button and then click on ``Deploy``.

1. In Toolchains, click on Delivery Pipeline to watch while the app is deployed. Once deployed, the app can be viewed by clicking `View app`.

1. To see the app and services created and configured for this code pattern, use the IBM Cloud dashboard. The app is named [app-name] with a unique suffix. The following services are created and easily identified by the [chosen prefix] prefix:
    * prefix-Service1
    * prefix-Service2

## Run locally
> NOTE: These steps are only needed when running locally instead of using the ``Deploy to IBM Cloud`` button.

<!-- there are MANY updates necessary here, just screenshots where appropriate -->

1. [Clone the repo](#1-clone-the-repo)
1. [Install the prerequisites](#2-install-the-prerequisites)
1. [Run the server](#3-run-the-server)
1. [Create a Cloudant or CouchDB service](#4-create-a-cloudant-or-couchdb-service)

### 1. Clone the repo

Clone the `shopping-list-polymer-pouchdb` locally. In a terminal, run:

<!-- when listing OS commands prefix it with $ (to indicate a command prompt) -->
<!-- this makes it visually easier to distinguish code from commands -->
```
$ git clone https://github.com/ibm-watson-data-lab/shopping-list-polymer-pouchdb
```

### 2. Install the prerequisites

First, install [Polymer CLI](https://github.com/Polymer/polymer-cli) using [npm](https://www.npmjs.com/) (we assume you have pre-installed [Node.js](https://nodejs.org/)):

<!-- when listing OS commands prefix it with $ (to indicate a command prompt) -->
<!-- this makes it visually easier to distinguish code from commands -->

    $ npm install --global polymer-cli

Second, install [Bower](https://bower.io/) using [npm](https://www.npmjs.com):

    $ npm install --global bower

Third, install the [Bower npm resolver](https://github.com/mjeanroy/bower-npm-resolver):

    $ npm install --global bower-npm-resolver

### 3. Run the server

This command serves the app at `http://127.0.0.1:8081` and provides basic URL routing for the app:

<!-- when listing OS commands prefix it with $ (to indicate a command prompt) -->
<!-- this makes it visually easier to distinguish code from commands -->

    $ polymer serve

### 4. Create a Cloudant or CouchDB service

PouchDB can synchronize with CouchDB and compatible servers. To run and test locally, you can install CouchDB. Alternatively, you can use a hosted Cloudant NoSQL DB service for your remote DB.

#### Installing Apache CouchDB

[Install CouchDB 2.1](http://docs.couchdb.org/en/2.1.0/install/index.html). Instructions are available for installing CouchDB 2.1 on Unix-like systems, on Windows, on Mac OS X, on FreeBSD, and via other methods.

Configure CouchDB for a [single-node setup](http://docs.couchdb.org/en/2.1.0/install/setup.html#single-node-setup), as opposed to a cluster setup. Once you have finished setting up CouchDB, you should be able to access CouchDB at `http://127.0.0.1:5984/`. Ensure that CouchDB is running and take note of your admin username and password.

#### Creating a Cloudant NoSQL DB service

To provision a managed Cloudant NoSQL DB

* Log in to [IBM Cloud](https://console.ng.bluemix.net/).
   > Sign up for an account, if you do not already have one.
* [Provision a Cloudant NoSQL DB _Lite_ plan instance](https://console.bluemix.net/catalog/services/cloudant-nosql-db), which is free.
  > If desired, you can also re-use an existing Cloudant NoSQL DB service instance. (Open the [**Data & Analytics**  resources dashboard](https://console.bluemix.net/dashboard/data) to see a list of pre-provisioned instances that you have access to.) 
 * Open the **Service credentials** tab.
* Add new credentials for this service instance if no credentials have been defined yet.
* View the credentials and note the value of the **url** property, which has the following format: `https://username:password@username-bluemix.cloudant.com`.

Tip: Select the **Manage** tab and click **Launch** to open the Cloudant dashboard and manage the service instance.

## Database and replication setup
1. [Create the remote database](#1-create-the-remote-database)
1. [Enable CORS](#2-enable-cors)
1. [Set the replication target](#3-set-the-replication-target)

### 1. Create the remote database

* Use the Cloudant or CouchDB dashboard to create a database.

* Select the Databases tab on the left and then use the `Create Database` button to create the "shopping-list" database.
The Shopping List app can be used locally before the database exists, but cannot sync
until the remote database is completed.

<!-- replace the screen shot if required -->
![](doc/source/images/create_db.png)

### 2. Enable CORS

* Open the Cloudant or CouchDB dashboard to enable Cross-Origin Resource Sharing (CORS).  

* Select the Account Settings (or config) tab and open the **CORS** tab.

* Enable CORS and restrict the domain as needed for security.

<!-- replace the screen shot (this should be required because the application URL is displayed) -->
![](doc/source/images/enable_cors.png)

### 3. Set the replication target

Run the Shopping List app and use the *Settings* form to enter your database URL.
If you use the IBM Cloud Cloudant URL taken from the service credentials as described above, the URL includes user name and password.

Add `/shopping-list` to the URL to connect to the database that you created.

<!-- replace the screen shot (this should be required) -->
![](doc/source/images/replicator.png)

<!--Edit as appropriate, update screenshot-->
# Using the app

The app allows you to create a shopping list by clicking on the plus sign. Click on the list to see its items. Then, you can add items to the list by clicking the plus sign. There is a checkbox to allow you to mark the items complete as you buy load up your cart.

When you have not configured your Replication Target or when you are offline, the lists will not sync. One good way to test this is to run two browsers. You can use Chrome and Firefox and have different lists in each.

When you go online and have the database and CORS enabled and the Replication Target is set, the shopping lists will sync. You will then be able to use both lists from either browser.

<!-- add/replace screen capture(s) -->
![](doc/source/images/shopping_lists.png)

## Running the tests

<!-- replace with test information, if there are tests defined -->
This project does not, at present, have any automated tests. If you'd like to contribute some then please raise and issue and submit a pull-request - we'd be very happy to add them! Any pull-request you contribute will run through our continuous integration process which will check your code style.

## Deploying to GitHub Pages

<!-- remove this section (and the dependent sub-sections) if the repo is not enabled for metrics cllection --> 
# Privacy Notice
<!-- No change required. Only link to the "master" privacy notice; this avoids duplication of content and -->
<!-- conflictingf information should the underlying metrics infrastructure change -->

Refer to https://github.com/IBM/metrics-collector-service#privacy-notice.

## Disabling Deployment Tracking

<!-- Update the instructions as required -->
To disable tracking, simply remove ``require('metrics-tracker-client').track();`` from the ``app.js`` file in the top level directory.

<!--Include any relevant links-->

# Links
* [More Shopping List Sample Apps](https://github.com/ibm-watson-data-lab/shopping-list)
<!--Keep the link to the main repo (above) in your list. Update the remainder of the list based on what's relevant for your specific project.-->
* [Offline First](http://offlinefirst.org/)
* [Progressive Web Apps](https://developers.google.com/web/progressive-web-apps/)
* [Service Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers)
* [Web App Manifest](https://w3c.github.io/manifest/)
* [PouchDB](https://pouchdb.com/)
* [Apache CouchDB](https://couchdb.apache.org/)
* [IBM Cloudant](https://www.ibm.com/cloud/cloudant)
* [Materialize CSS](http://materializecss.com/getting-started.html)
* [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

<!-- pick the relevant ones from below -->
# Learn more

* **Artificial Intelligence Code Patterns**: Enjoyed this Code Pattern? Check out our other [AI Code Patterns](https://developer.ibm.com/code/technologies/artificial-intelligence/).
* **Data Analytics Code Patterns**: Enjoyed this Code Pattern? Check out our other [Data Analytics Code Patterns](https://developer.ibm.com/code/technologies/data-science/)
* **AI and Data Code Pattern Playlist**: Bookmark our [playlist](https://www.youtube.com/playlist?list=PLzUbsvIyrNfknNewObx5N7uGZ5FKH0Fde) with all of our Code Pattern videos
* **With Watson**: Want to take your Watson app to the next level? Looking to utilize Watson Brand assets? [Join the With Watson program](https://www.ibm.com/watson/with-watson/) to leverage exclusive brand, marketing, and tech resources to amplify and accelerate your Watson embedded commercial solution.
* **Data Science Experience**: Master the art of data science with IBM's [Data Science Experience](https://datascience.ibm.com/)
* **PowerAI**: Get started or get scaling, faster, with a software distribution for machine learning running on the Enterprise Platform for AI: [IBM Power Systems](https://www.ibm.com/ms-en/marketplace/deep-learning-platform)
* **Spark on IBM Cloud**: Need a Spark cluster? Create up to 30 Spark executors on IBM Cloud with our [Spark service](https://console.bluemix.net/catalog/services/apache-spark)
* **Kubernetes on IBM Cloud**: Deliver your apps with the combined the power of [Kubernetes and Docker on IBM Cloud](https://www.ibm.com/cloud-computing/bluemix/containers)

<!--keep this-->

# License
[Apache 2.0](LICENSE)
