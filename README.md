# nodejs-google-cloud-platform
NodeJS - Google Cloud Platform

# Node.js and Google Cloud Platform

Based on 'Node.js and Google Cloud Platform' at https://cloud.google.com/community/tutorials/running-nodejs-on-google-cloud

There are four options for running Node.js applications on Google Cloud Platform:

- Google Compute Engine

- Google Container Engine

- Google App Engine flexible environment

- Google Cloud Functions

## Node.js on Compute Engine

Hosting a Node.js application on [Compute Engine](https://cloud.google.com/compute/) is just like hosting a Node.js application on a traditional Virtual Private Server (VPS)—you have complete control of the virtual machine. Google Compute Engine delivers virtual machines running in Google's innovative data centers and worldwide fiber network. Compute Engine's tooling and workflow support enable scaling from single instances to global, load-balanced cloud computing.

## Node.js on Container Engine

[Container Engine](https://cloud.google.com/container-engine/) is a powerful cluster manager and orchestration system for running your Docker containers. Container Engine schedules your containers into the cluster and manages them automatically based on requirements you define (such as CPU and memory). It's built on the open source Kubernetes system, giving you the flexibility to take advantage of on-premises, hybrid, or public cloud infrastructure. With it you can orchestrate containerized Node.js deployments using Kubernetes' container management infrastructure.

## Node.js on App Engine flexible environment

[App Engine flexible environment](https://cloud.google.com/appengine/docs/flexible/nodejs/) is a fully managed, Docker-based Platform-as-a-Service (PaaS). You can deploy, monitor, and scale Node.js applications without having to know anything about virtual machines, containers, or compute infrastructure. Google manages your Node.js application for you.

## Node.js on Cloud Functions

[Cloud Functions](https://cloud.google.com/functions/) is a lightweight, event-based, asynchronous compute solution that allows you to create small, single-purpose functions that respond to cloud events without the need to manage a server or a runtime environment. You deploy individual functions written in Node.js that are executed in response to various cloud events, including direct HTTP requests.

# How to Prepare a Node.js Development Environment

Based on 'How to Prepare a Node.js Development Environment' at https://cloud.google.com/community/tutorials/how-to-prepare-a-nodejs-dev-environment

## Install Node Version Manager (NVM) - optional

[Node Version Manager](https://github.com/creationix/nvm) (NVM) is a simple bash script for managing (multiple) installations of Node.js and NPM. NVM does not support Windows, check out [nvm-windows](https://github.com/coreybutler/nvm-windows) for managing your Node.js installation on Windows.

Installing NVM is simple, check out the [installation instructions](https://github.com/creationix/nvm#installation) for details on installing NVM on your platform.

## Install Node.js and NPM

You can install Node.js and NPM from the website nodejs.com.

You can check what version of Node.js you're running with:

```javascript
node -v
```

NPM is the Node Package Manager for Node.js should have been installed alongside Node.js. 

For additional reading, read [Run Express.js on Google Cloud Platform](https://cloud.google.com/community/tutorials/run-expressjs-on-google-app-engine).

## Install an editor

Popular editors (in no particular order) used to develop Node.js applications include, but are not limited to:

- [Visual Studio Code](https://code.visualstudio.com/) by Microsoft

## Install the Google Cloud SDK

The [Google Cloud SDK](https://cloud.google.com/sdk/) is a set of tools for Cloud Platform. It contains ```gcloud```, ```gsutil```, and ```bq```, which you can use to access Google Compute Engine, Google Cloud Storage, Google BigQuery, and other products and services from the command-line. You can run these tools interactively or in your automated scripts.

As an example, here is a simple command that will deploy any Node.js web application to Google App Engine flexible environment (after deployment it App Engine attempt to start the application with npm start):

```javascript
gcloud app deploy
```

## Install the Google Cloud Client Library for Node.js

The Google Cloud Client Library for Node.js is the idiomatic way for Node.js developers to integrate with Google Cloud Platform services, like Cloud Datastore and Cloud Storage. You can install the entire suite of libraries with:

```javascript
npm install google-cloud
```

or you can install the package for an individual API, like Cloud Storage for example:

```javascript
npm install @google-cloud/storage
```




