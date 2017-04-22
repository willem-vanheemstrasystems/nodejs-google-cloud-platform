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

# Deploy and run Hello World on App Engine

To deploy your app to the App Engine flexible environment:

Deploy the Hello World app by running the following command from the project directory:

```javascript
gcloud app deploy
```

You will be prompted as follows:

```
 - hello-world-with-nodejs-159121/default/20170422t150709 (from [C:\Users\user\git\Willem-vanHeemstraSy
stems\nodejs-google-cloud-platform\nodejs-google-cloud-platform\NDJS_GC_001\app.yaml])
     Deploying to URL: [https://hello-world-with-nodejs-159121.appspot.com]

     Do you want to continue (Y/n)?
```

Confirm by typing: Y <followed by ENTER>

Learn about the optional flags.

Note: During deployment npm install is used by default to install dependencies unless a yarn.lock file exists and is not listed in the app.yaml file's skip_files section, in which case yarn install --production is used instead. To cause the build to fall back to npm install delete the yarn.lock file or add yarn.lock to the skip_files section of your app.yaml file.

Launch your browser and view the app at http://YOUR_PROJECT_ID.appspot.com, by running the following command:

```javascript
gcloud app browse
```

This time, the page that displays the Hello World message is delivered by a web server running on an App Engine instance.
Congratulations! You've deployed your first Node.js app to App Engine flexible environment!

See the following sections for information about cleaning up as well as links to the possible next steps that you can take.

## Clean up

To avoid incurring charges, you can delete your Cloud Platform project to stop billing for all the resources used within that project.

***Warning***: Deleting a project has the following consequences:

- If you used an existing project, you'll also delete any other work you've done in the project.

- You can't reuse the project ID of a deleted project. If you created a custom project ID that you plan to use in the future, you should delete the resources inside the project instead. This ensures that URLs that use the project ID, such as an appspot.com URL, remain available.

1) In the Cloud Platform Console, [go to the Projects page](https://console.cloud.google.com/iam-admin/projects?_ga=1.31321276.204866641.1492336447).

2) In the project list, select the project you want to delete and click ***Delete project***.

3) In the dialog, type the project ID, and then click ***Shut down*** to delete the project.

## Hello World code review

Hello World is the simplest possible App Engine app, as it contains only one service, has only one version, and all of the code is located within the app's root directory. This section describes each of the app files in detail.

