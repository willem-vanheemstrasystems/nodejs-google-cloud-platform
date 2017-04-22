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

Configuring your deployment

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

