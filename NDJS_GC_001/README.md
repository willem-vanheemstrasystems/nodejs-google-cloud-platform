### README.md

# NDJS_GC_001

Based on 'How to prepare a nodejs dev environment' at https://cloud.google.com/community/tutorials/how-to-prepare-a-nodejs-dev-environment

## Install the Google Cloud Client Library for Node.js

The Google Cloud Client Library for Node.js is the idiomatic way for Node.js developers to integrate with Google Cloud Platform services, like Cloud Datastore and Cloud Storage. You can install the entire suite of libraries with:

```javascript
npm install google-cloud
```

or you can install the package for an individual API, like Cloud Storage for example:

```javascript
npm install @google-cloud/storage
```

## Authentication

During local development, your Node.js application must authenticate itself in order to interact Google Cloud Platform APIs. The easiest way to get started is to run the following command after installing the [Google Cloud SDK](https://cloud.google.com/sdk/):

```javascript
gcloud beta auth application-default login
```

This will save credentials to your machine that the Cloud Client Library will automatically use to authenticate. Read more about [authentication](https://cloud.google.com/docs/authentication#getting_credentials_for_server-centric_flow), including how authentication is handled once your application is deployed.

You'll also want to tell the Cloud Client Library which Google Platform Project to use. You do this by setting the ```GCLOUD_PROJECT``` environment variable to your project ID, or by passing a projectId option to the library in your code. 

## Install other useful tools

For a comprehensive list of amazing Node.js tools and libraries, check out the curated [Awesome Node.js list](https://github.com/sindresorhus/awesome-nodejs).

## Google App Engine Node.js Flexible Environment Documentation

Based on 'Google App Engine Node.js Flexible Environment Documentation' at https://cloud.google.com/appengine/docs/flexible/nodejs/

The App Engine flexible environment is based on Google Compute Engine and automatically scales your app up and down while balancing the load.

### Quickstart

Based on 'Quickstart for Node.js in the App Engine Flexible Environment' at https://cloud.google.com/appengine/docs/flexible/nodejs/quickstart

This quickstart shows you how to create a small Node.js App Engine application written with the Express.js framework that displays a short message.

Source: https://github.com/GoogleCloudPlatform/nodejs-docs-samples

# Run Hello World on your local machine

Install dependencies for this project by entering the following command:

```javascript
npm install
```

Run the start script.

```javascript
npm start
```

In your web browser, enter the following address:

http://localhost:8080

You can see the Hello World message from the sample app displayed in the page.

In your terminal window, press Ctrl+C to exit the web server.

