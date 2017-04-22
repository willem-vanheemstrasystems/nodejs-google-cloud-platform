### README.md

# Your first app with Node.js on Google Cloud Platform

We will be deploying to the following project:

- Website (long-temple-164810) of organisation [gruniart](https://console.cloud.google.com/appengine/create?lang=nodejs&project=long-temple-164810&organizationId=504198024290)

## App Engine Quickstart

Google Cloud Platform organizes resources into projects. This allows you to collect all the related resources for a single application in one place.

Please confirm this project to be used in the tutorial:

- Website (long-temple-164810)

Click 'Continue'.

View Sample Code

We have the sample Node.js code prepared for you in the Google Cloud Repository. To view your cloned code, open the menu on the left side of the console and select Development.

### Configuring your deployment

1 YAML files

Google App Engine uses YAML files to specify a deployment's configuration. The ***app.yaml*** file configures the deployment environment.

```javascript
#	Copyright 2017, Google, Inc.
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
# [START runtime]
runtime: nodejs
env: flex
# [END runtime]

```

2 Exploring app.yaml

app.yaml files contain information about your application, like the runtime environment, URL handlers, and more. Expand each section below to learn about the details.

***Runtime***:

runtime is one of the required keys for VM hosting environment setup. For standard runtimes, use values python27, go, java, php, ruby, nodejs. For custom runtimes, use value custom.

The runtime, vm, api_version keys are required to setup the VM hosting environment. Note that when using custom runtime, although api_version must be given, the value is ignored.

***Resources Allocation***:

resources defines the machine type that App Engine will use to serve your app based on the amount of CPU and memory you've specified. The machine is guaranteed to have at least the level of resources you've specified, it might have more.

cpu is the number of CPU cores that the machine should have.

memory_gb is the amount of RAM in Gigabytes that the machine type should have.

disk_size_gb is the size of Persistent Disk in Gigabytes that the machine type should have.

***Scaling Settings***:

automatic_scaling defines how your application should scale to use more or less VM instances based on the value you specify for target CPU utilization.

min_number_instances is the minumum number of VM instances that your app will be served from as it is scaled down.

max_number_instances is the maximum number of VM instances that your app will be served from as it is scaled up.

cool_down_period_sec is the time interval in seconds between auto scaling checks. The cool-down period must be greater than or equal to 60 seconds.

target_utilization is used by the autoscaling service to decide when to reduce or increase the number of VM instances based on the average CPU utilization across all running VM instances.

***Other***:

Use the env_variables to define environment variables that then can be accessed from your app's code. Here the environment variable "NODE_ENV" is set to be "production".

From the Node.js code in your app you can access this variable's value using the following code:

var env = process.env.NODE_ENV;

### Using Google Cloud Shell

Cloud Shell is a built-in command line tool for the console. We're going to use Cloud Shell to deploy our app.

1. Using Google Cloud Shell

Open the Google Cloud Shell on the Web console using the [>_] button.

You will be prompted as follows:

```javascript
Welcome to Cloud Shell! Type "help" to get started.
lana_gruni@long-temple-164810:~$
```

where 'lana_gruni' is the user with which you are logged in, and 'long-temple-164810' is the project name.

2. Clone the sample code

Use Cloud Shell to clone and navigate to the "Hello World" code. The sample code is cloned from your project repository to the Cloud Shell.

In Cloud Shell enter:

```javascript
TUTORIALDIR=~/src/long-temple-164810/nodejs_mvms_quickstart-2017-04-22-15-26
```

Clone a sample repository:

```javascript
git clone https://github.com/GoogleCloudPlatform/nodejs-getting-started.git $TUTORIALDIR
```

You will be prompted with:

```javascript
Cloning into '/home/lana_gruni/src/long-temple-164810/nodejs_mvms_quickstart-2017-04-22-15-26'...
remote: Counting objects: 1540, done.
remote: Compressing objects: 100% (79/79), done.
remote: Total 1540 (delta 67), reused 21 (delta 21), pack-reused 1438
Receiving objects: 100% (1540/1540), 460.51 KiB | 0 bytes/s, done.
Resolving deltas: 100% (1071/1071), done.
```

Switch to the tutorial directory:

```javascript
cd $TUTORIALDIR/1-hello-world
```

You will be prompted with:

```javascript
lana_gruni@long-temple-164810:~/src/long-temple-164810/nodejs_mvms_quickstart-2017-04-22-15-26/1-hello-world$
```

Testing your app

1. Install npm packages

We will install the npm packages on Cloud Shell in order to test run the Node.js app.

To install npm packages, enter:

```javascript
npm install --production
```

2 Test your app on Cloud Shell

Cloud Shell lets you test your app before deploying to make sure it's running as intended, just like debugging on your local machine.

To test your app enter:

```javascript
npm start
```

You will be prompted with:

```javascript
> nodejs-getting-started@1.0.0 start /home/lana_gruni/src/long-temple-164810/nodejs_mvms_quickstart-2017-04-22-15-26/1-hello-world
> node app.js

App listening on port 8081
```

3 Preview your app with "Web preview"

Your app is now running on Cloud Shell. You can access the app by using "Web preview" [^]  to connect to port 8080.

The [^] button is found along the menu bar along the Cloud Shell.

4 Terminating the preview instance

Terminate the instance of the application by pressing Ctrl+C in the Cloud Shell.

