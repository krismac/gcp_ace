Exam Notes
GCP commands that works in the google shell
Key points that are extracted from Google Cloud links

Topic wise Notes and Exam Tips are given below:
Setting up cloud projects and accounts
https://cloud.google.com/resource-manager/docs/creating-managing-projects

Creating projects
https://cloud.google.com/sdk/gcloud/reference/projects/create

Assigning users to pre-defined IAM roles within a project https://cloud.google.com/sdk/gcloud/reference/projects/add-iam-policy-binding

Linking users to G Suite identities https://support.google.com/cloudidentity/answer/7319251?hl=en

Enabling APIs within projects
<https://cloud.google.com/service-management/enable-disable>
<https://cloud.google.com/sdk/gcloud/reference/services/>
https://cloud.google.com/sdk/gcloud/reference/services/list
https://cloud.google.com/sdk/gcloud/reference/services/enable
https://cloud.google.com/sdk/gcloud/reference/services/disable

Provisioning one or more Stackdriver accounts https://cloud.google.com/monitoring/accounts/

Managing billing configuration
Creating one or more billing accounts https://cloud.google.com/billing/docs/how-to/manage-billing-account
Linking projects to a billing account https://cloud.google.com/sdk/gcloud/reference/beta/billing/projects/link
Establishing billing budgets and alerts https://cloud.google.com/billing/docs/how-to/budgets
Setting up billing exports to estimate daily/monthly charges
https://cloud.google.com/billing/docs/how-to/export-data-file
https://cloud.google.com/billing/docs/how-to/export-data-bigquery
https://cloud.google.com/billing/docs/how-to/bq-examples

Installing and configuring the command line interface (CLI), specifically the Cloud SDK (e.g., setting the default project).
Install:
https://hub.docker.com/r/google/cloud-sdk/~/dockerfile/
https://cloud.google.com/sdk/docs/quickstart-linux
To set the project property in the core section, run:
# gcloud config set project myProject
To set the zone property in the compute section, run:
# gcloud config set compute/zone asia-east1-b
Planning and configuring a cloud solution
Planning and estimating GCP product use using the Pricing Calculator
https://cloud.google.com/products/calculator/
Google Cloud Platform on a shoestring budget (Google I/O ‘18)
Planning and configuring compute resources
Selecting appropriate compute choices for a given workload
Deciding between Compute Engine, Container Engine, App Engine and more (Google Cloud Next ‘17)
Compute Engine
Compute Engine is, basically, kind of everything else, or even all of those things if you want. It’s VM. So you have full control to do whatever you need to do to connect things together. It’s also a really good fit for existing systems.
Kubernetes Engine
Container Engine is a system of containers working together to solve your problems.
App Engine
Get to know Google App Engine
App Engine is focused on making your web code run extremely well. It’s optimized for that. And it’s code first kind of thinking.
Using preemptible VMs and custom machine types as appropriate
// CREATE INSTANCE WITH 4 vCPUs and 5 GB MEMORY #gcloud compute instances create my-vm — custom-cpu 4 — custom-memory 5
// ENABLE PREEMPTIBLE OPTION #gcloud compute instances create my-vm — zone us-central1-b — preemptible
2.3 — Planning and configuring data storage options
From blobs to relational tables: Where do I store my Data? (Google Cloud Next ‘17)

Product choice
Cloud SQL
https://cloud.google.com/sql/docs/
Cloud SQL is a fully-managed database service that makes it easy to set up, maintain, manage, and administer your relational databases on Google Cloud Platform.
BigQuery
https://cloud.google.com/bigquery/
A fast, highly scalable, cost-effective and fully-managed enterprise data warehouse for analytics at any scale
BigQuery is Google’s serverless, highly scalable, low cost enterprise data warehouse designed to make all your data analysts productive. Because there is no infrastructure to manage, you can focus on analyzing data to find meaningful insights using familiar SQL and you don’t need a database administrator. BigQuery enables you to analyze all your data by creating a logical data warehouse over managed, columnar storage as well as data from object storage, and spreadsheets. BigQuery makes it easy to securelyshare insights within your organization and beyond as datasets, queries, spreadsheets and reports. BigQuery allows organizations tocapture and analyze data in real-time using its powerful streaming ingestion capability so that your insights are always current. BigQuery is free for up to 1TB of data analyzed each month and 10GB of data stored.
Cloud Spanner
https://cloud.google.com/spanner/
The first horizontally scalable, strongly consistent, relational database service

Cloud Bigtable
https://cloud.google.com/bigtable/
Choosing storage options
https://cloud.google.com/storage/docs/gsutil/commands/mb
https://cloud.google.com/storage/docs/storage-classes
Regional
Storing frequently accessed in the same region as your Google Cloud DataProc or Google Compute Engine instances that use it, such as for data analytics.
Multi-regional
Storing data that is frequently accessed (“hot” objects) around the world, such as serving website content, streaming videos, or gaming and mobile applications.
Nearline
Data you do not expect to access frequently (i.e., no more than once per month). Ideal for back-up and serving long-tail multimedia content.
Coldline
Data you expect to access infrequently (i.e., no more than once per year). Typically this is for disaster recovery, or data that is archived and may or may not be needed at some future time.
StorageClass
Characteristics
Use Cases
Price (per GB per month)**
Multi-Regional Storage
>99.99% typical monthly availability
99.95% availability SLA*
Geo-redundant
Storing data that is frequently accessed (“hot” objects) around the world, such as serving website content, streaming videos, or gaming and mobile applications.
$0.026
Regional Storage
99.99% typical monthly availability
99.9% availability SLA*
Lower cost per GB stored
Data stored in a narrow geographic region
Redundant across availability zones
Storing frequently accessed in the same region as your Google Cloud DataProc or Google Compute Engine instances that use it, such as for data analytics.
$0.02
Nearline Storage
99.9% typical monthly availability
99.0% availability SLA*
Very low cost per GB stored
Data retrieval costs
Higher per-operation costs
30-day minimum storage duration
Data you do not expect to access frequently (i.e., no more than once per month). Ideal for back-up and serving long-tail multimedia content.
$0.01
Coldline Storage
99.9% typical monthly availability
99.0% availability SLA*
Lowest cost per GB stored
Data retrieval costs
Higher per-operation costs
90-day minimum storage duration
Data you expect to access infrequently (i.e., no more than once per year). Typically this is for disaster recovery, or data that is archived and may or may not be needed at some future time.
$0.007
Planning and configuring network resources
Differentiating load balancing options
https://cloud.google.com/files/internal-load-balancing-tutorial-slides.pdf
https://cloud.google.com/compute/docs/load-balancing/internal/
Identifying resource locations in a network for availability
Configuring Cloud DNS
https://cloud.google.com/dns/quickstart
Deploying and implementing a cloud solution
Deploying and implementing Compute Engine resources
Launching a compute instance using Cloud Console and Cloud SDK (gcloud)
https://cloud.google.com/sdk/gcloud/reference/compute/instances/create
Assign disks
[ — disk=[auto-delete=AUTO-DELETE],[boot=BOOT],[device-name=DEVICE-NAME],[mode=MODE],[name=NAME]]
https://cloud.google.com/sdk/gcloud/reference/compute/instances/attach-disk
Availability policy
SSH keys
Creating an autoscaled managed instance group using an instance template
https://cloud.google.com/compute/docs/autoscaler/#managed_instance_groups
https://cloud.google.com/compute/docs/instance-groups/
https://cloud.google.com/compute/docs/instance-templates/
You can create two types of managed instance groups:
A zonal managed instance group, which contains instances from the same zone.
A regional managed instance group, which contains instances from multiple zones across the same region.
Generating/uploading a custom SSH key for instances
https://cloud.google.com/compute/docs/instances/adding-removing-ssh-keys
Configuring a VM for Stackdriver monitoring and logging
https://cloud.google.com/logging/docs/agent/installation
Assessing compute quotas and requesting increases
https://console.cloud.google.com/iam-admin/quotas?project=xxx
https://cloud.google.com/compute/quotas
https://cloud.google.com/appengine/quotas
https://cloud.google.com/pubsub/quotas
https://cloud.google.com/bigquery/quotas
https://cloud.google.com/bigquery/docs/custom-quotas
https://cloud.google.com/functions/quotas
https://cloud.google.com/datastore/pricing
https://cloud.google.com/deployment-manager/pricing-and-quotas
https://cloud.google.com/monitoring/quotas
https://cloud.google.com/logging/quotas
https://cloud.google.com/endpoints/docs/openapi/quotas-configure
3.1.6 — Installing the Stackdriver Agent for monitoring and logging
https://cloud.google.com/monitoring/agent/install-agent
Deploying and implementing Kubernetes Engine resources
Kubernetes Design and Architecture
Deploying a Kubernetes Engine cluster
https://cloud.google.com/kubernetes-engine/docs/how-to/creating-a-container-cluster
https://cloud.google.com/kubernetes-engine/docs/concepts/cluster-architecture
Deploying a container application to Kubernetes Engine using pods
gcloud config set container/cluster [CLUSTER_NAME]
gcloud container clusters get-credentials [CLUSTER_NAME]
Configuring Kubernetes Engine application monitoring and logging
https://kubernetes.io/docs/tasks/debug-application-cluster/logging-stackdriver/
# gcloud beta container clusters update — logging-service=none CLUSTER
# kubectl get ds fluentd-gcp-v2.0 — namespace kube-system -o yaml > fluentd-gcp-ds.yaml
# kubectl replace -f fluentd-gcp-ds.yaml
Deploying and implementing App Engine and Cloud Functions resources
Deploying an application to App Engine

Scaling configuration
https://cloud.google.com/appengine/docs/standard/python/how-instances-are-managed
The scaling type you assign to a service determines the whether its instances are resident or dynamic:
Auto scaling services use dynamic instances.
Manual scaling services use resident instances.
Basic scaling services use dynamic instances.
Manual scaling
A service with manual scaling use resident instances that continuously run the specified number of instances irrespective of the load level. This allows tasks such as comple initializations and applications that rely on the state of the memory over time.
Automatic scaling
Auto scaling services use dynamic instances that get created based on request rate, response latencies, and other application metrics. However, if you specify a number of minimum idle instances, that specified number of instances run as resident instances while any additional instances are dynamic.
Basic Scaling
A service with basic scaling use dynamic instances. Each instance is created when the application receives a request. The instance will be turned down when the app becomes idle. Basic scaling is ideal for work that is intermittent or driven by user activity.
Versions
The recommended approach is to remove the version element from your app.yaml file and instead, use a command-line flag to specify your version ID:
https://cloud.google.com/appengine/docs/admin-api/deploying-apps
#gcloud app deploy -v [YOUR_VERSION_ID]
#appcfg.py update -V [YOUR_VERSION_ID]
Traffic splitting
https://cloud.google.com/sdk/gcloud/reference/app/services/set-traffic
Deploying a Cloud Function that receives Google Cloud events
Cloud Pub/Sub events
https://cloud.google.com/functions/docs/tutorials/pubsub
Cloud Storage object change notification events
https://cloud.google.com/functions/docs/calling/storage
Deploying and implementing data solutions
Initializing data systems with products
Cloud SQL
Cloud Datastore
Cloud Bigtable
BigQuery
Cloud Spanner
Cloud Pub/Sub
Cloud Dataproc
Cloud Storage
Loading data
Command line upload
API transfer
https://cloud.google.com/storage/transfer/reference/rest/
Import / export
https://cloud.google.com/sql/docs/mysql/import-export/
https://cloud.google.com/sql/docs/postgres/import-export/importing
https://cloud.google.com/sql/docs/postgres/import-export/
https://cloud.google.com/datastore/docs/export-import-entities
Load data from Cloud Storage
Streaming data to Cloud Pub/Sub
https://cloud.google.com/pubsub/docs/quickstart-cli
Deploying and implementing networking resources
Creating a VPC with subnets
Custom-mode VPC
Shared VPC
Launching a Compute Engine instance with custom network configuration
https://cloud.google.com/sdk/gcloud/reference/compute/networks/subnets/create
Internal-only IP address
[ — enable-private-ip-google-access]
Enable/disable access to Google Cloud APIs from this subnet for instances without a public ip address.
Google private access
https://cloud.google.com/sdk/gcloud/reference/compute/instances/create
[ — private-network-ip=PRIVATE_NETWORK_IP]
Static external and private IP address
[ — address=ADDRESS | — no-address]
Network tags
[ — tags=TAG,[TAG,…]]
Creating ingress and egress firewall rules for a VPC
https://cloud.google.com/sdk/gcloud/reference/compute/firewall-rules/
[ — direction=DIRECTION]
If direction is NOT specified, then default is to apply on incoming traffic. For incoming traffic, it is NOT supported to specify destination-ranges; For outbound traffic, it is NOT supported to specify source-ranges or source-tags.
For convenience, ‘IN’ can be used to represent ingress direction and ‘OUT’ can be used to represent egress direction.
DIRECTION must be one of: INGRESS, EGRESS, IN, OUT.
IP subnets
[ — source-ranges=CIDR_RANGE,[CIDR_RANGE,…]]
A list of IP address blocks that are allowed to make inbound connections that match the firewall rule to the instances on the network. The IP address blocks must be specified in CIDR format: http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing.
If neither — source-ranges nor — source-tags are specified, — source-ranges defaults to 0.0.0.0/0, which means that the rule applies to all incoming connections from inside or outside the network. If both — source-ranges and — source-tags are specified, the rule matches if either the range of the source matches — source-ranges or the tag of the source matches — source-tags.
If neither — source-ranges nor — source-tags is provided, then this flag will default to 0.0.0.0/0, allowing all sources. Multiple IP address blocks can be specified if they are separated by commas.
[ — destination-ranges=CIDR_RANGE,[CIDR_RANGE,…]]
The firewall rule will apply to traffic that has destination IP address in these IP address block list. The IP address blocks must be specified in CIDR format:http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing.
If — destination-ranges is NOT provided, then this flag will default to 0.0.0.0/0, allowing all destinations. Multiple IP address blocks can be specified if they are separated by commas.
Tags
[ — source-tags=TAG,[TAG,…]]
A list of instance tags indicating the set of instances on the network to which the rule applies if all other fields match. If neither — source-ranges nor — source-tags are specified, — source-ranges defaults to 0.0.0.0/0, which means that the rule applies to all incoming connections from inside or outside the network.
If both — source-ranges and — source-tags are specified, an inbound connection is allowed if either the range of the source matches — source-ranges or the tag of the source matches — source-tags.
Tags can be assigned to instances during instance creation.
If source tags are specified then neither a source nor target service account can also be specified.
[ — target-tags=TAG,[TAG,…]]
A list of instance tags indicating the set of instances on the network which may accept inbound connections that match the firewall rule. If both target tags and target service account are omitted, all instances on the network can receive inbound connections that match the rule.
Tags can be assigned to instances during instance creation.
If target tags are specified then neither a source nor target service account can also be specified.
Service accounts
[ — source-service-accounts=EMAIL,[EMAIL,…]]
The email of a service account indicating the set of instances on the network which match a traffic source in the firewall rule.
If a source service account is specified then neither source tags nor target tags can also be specified.
[ — target-service-accounts=EMAIL,[EMAIL,…]]
The email of a service account indicating the set of instances to which firewall rules apply. If both target tags and target service account are omitted, the firewall rule is applied to all instances on the network.
If a target service account is specified then neither source tag nor target tags can also be specified.
Creating a VPN between a Google VPC and an external network using Cloud VPN
https://cloud.google.com/vpn/docs/concepts/overview
https://cloud.google.com/vpn/docs/how-to/creating-vpns
Creating a load balancer to distribute application network traffic to an application
Global HTTP(S) load balancer
https://cloud.google.com/compute/docs/load-balancing/http/
Global SSL Proxy load balancer
https://cloud.google.com/compute/docs/load-balancing/tcp-ssl/
Global TCP Proxy load balancer
https://cloud.google.com/compute/docs/load-balancing/tcp-ssl/tcp-proxy
Regional Network load balancer
https://cloud.google.com/compute/docs/load-balancing/network/
Regional Internal load balancer
https://cloud.google.com/solutions/internal-load-balancing-haproxy
Deploying a Solution using Cloud Launcher
Browsing Cloud Launcher catalog and viewing solution details
https://console.cloud.google.com/launcher
Deploying a Cloud Launcher marketplace solution
https://console.cloud.google.com/launcher
Deploying an Application using Deployment Manager
Developing Deployment Manager templates to automate deployment of an application
https://github.com/GoogleCloudPlatform/deploymentmanager-samples
Launching a Deployment Manager template to provision GCP resources and configure an application automatically
VM with Startup Script
Creates a VM with user specified disks attached to it.
Cloud Functions Example
Cloud Container Builder Example
GKE Cluster and Type
Custom IAM Role
Ensuring successful operation of a cloud solution
Managing Compute Engine resources
Managing a single VM instance
Start
https://cloud.google.com/sdk/gcloud/reference/compute/instances/start
4.1.1.2 — stop
https://cloud.google.com/sdk/gcloud/reference/compute/instances/stop
4.1.1.3 — edit configuration
4.1.1.4 — delete an instance
https://cloud.google.com/sdk/gcloud/reference/compute/instances/delete
4.1.2 — SSH/RDP to the instance
https://cloud.google.com/compute/docs/instances/connecting-to-instance
4.1.3 — Attaching a GPU to a new instance and installing CUDA libraries
You can attach GPUs only to instances with a predefined machine type or custom machine type that you are able to create in a zone. GPUs are not supported on shared-core machine types or memory-optimized machine types.
https://cloud.google.com/compute/docs/gpus/add-gpus
[ACCELERATOR_COUNT] is the number of GPUs that you want to add to your instance. See GPUs on Compute Engine for a list of GPU limits based on the machine type of your instance.
[ACCELERATOR_TYPE] is the GPU model that you want to use. See GPUs on Compute Engine for a list of available GPU models.
Viewing current running VM Inventory
instance IDs
Details
Working with snapshots
Create a snapshot from a VM
https://cloud.google.com/compute/docs/disks/create-snapshots
https://cloud.google.com/sdk/gcloud/reference/compute/disks/create
— source-snapshot=SOURCE_SNAPSHOT
A source snapshot used to create the disks. It is safe to delete a snapshot after a disk has been created from the snapshot. In such cases, the disks will no longer reference the deleted snapshot. To get a list of snapshots in your current project, run gcloud compute snapshots list. A snapshot from an existing disk can be created using the gcloud compute disks snapshot command. This flag is mutually exclusive with — image.
When using this option, the size of the disks must be at least as large as the snapshot size. Use — size to adjust the size of the disks.
View snapshots
https://cloud.google.com/sdk/gcloud/reference/compute/snapshots/list
Delete a snapshot
https://cloud.google.com/sdk/gcloud/reference/compute/snapshots/delete
Working with Images
Create an image from a VM or a snapshot
https://cloud.google.com/sdk/gcloud/reference/compute/images/create
View images
https://cloud.google.com/sdk/gcloud/reference/compute/images/list
Delete an image
https://cloud.google.com/sdk/gcloud/reference/compute/images/delete
Working with Instance Groups
https://cloud.google.com/compute/docs/instance-groups/
https://cloud.google.com/compute/docs/instance-groups/updating-managed-instance-groups
Set auto scaling parameters
https://cloud.google.com/compute/docs/autoscaler/
Managed instance groups and autoscaling
Managed instance groups support autoscaling so you can dynamically add or remove instances from a managed instance group in response to increases or decreases in load. You enable autoscaling and choose an autoscaling policy to determine how you want to scale. Applicable autoscaling policies include scaling based on CPU utilization, load balancing capacity, Stackdriver monitoring metrics, or by a queue-based workload like Google Cloud Pub/Sub.
Because autoscaling requires adding and removing instances from a group, you can only use autoscaling with managed instance groups so the autoscaler can maintain identical instances. Autoscaling does not work on unmanaged instance groups, which can contain heterogeneous instances.
For more information, read Autoscaling Groups of Instances.
Assign instance template
https://cloud.google.com/compute/docs/instance-templates/
Create an instance template
https://cloud.google.com/compute/docs/instance-templates/create-instance-templates
https://cloud.google.com/sdk/gcloud/reference/compute/instance-groups/managed/create
Remove instance group
https://cloud.google.com/sdk/gcloud/reference/compute/instance-groups/managed/delete
Working with management interfaces
Cloud Console
Cloud Shell
https://cloud.google.com/shell/docs/how-cloud-shell-works
GCloud SDK
https://cloud.google.com/sdk/docs/
Managing Kubernetes Engine resources
https://kubernetes.io/docs/reference/kubectl/cheatsheet/
Viewing current running cluster inventory
nodes
# kubectl get nodes
pods
# kubectl get pods
services
# kubectl get services
Browsing the container image repository and viewing container image details
Working with nodes
https://cloud.google.com/kubernetes-engine/docs/how-to/resizing-a-container-cluster
add a node
https://cloud.google.com/sdk/gcloud/reference/container/clusters/resize
gcloud container clusters resize [CLUSTER_NAME] \
— node-pool [NODE_POOL] \
— size [SIZE]
edit a node
remove a node
Working with pods
add pods
edit pods
remove pods
Working with services
add a service
edit a service
remove a service
Working with management interfaces
Cloud Console
Cloud Shell
Cloud SDK
Managing App Engine resources
Adjusting application traffic splitting parameters
Setting scaling parameters for autoscaling instances
Working with management interfaces
Cloud Console
Cloud Shell
Cloud SDK
Managing data solutions
Executing queries to retrieve data from data instances
Cloud SQL
BigQuery
Cloud Spanner
Cloud Datastore
Cloud Bigtable
Cloud Dataproc
Estimating costs of a BigQuery query
https://cloud.google.com/bigquery/docs/estimate-costs
Backing up and restoring data instances
Cloud SQL
Cloud Datastore
Cloud Dataproc
Reviewing job status in Cloud Dataproc or BigQuery
Moving objects between Cloud Storage buckets
Converting Cloud Storage buckets between storage classes
Setting object lifecycle management policies for Cloud Storage buckets
Working with management interfaces
Cloud Console
Cloud Shell
Cloud SDK
Managing networking resources
Adding a subnet to an existing VPC
https://cloud.google.com/vpc/docs/using-vpc
Adding a new subnet to an existing VPC network
You can add a subnet to a region of an existing VPC network. The primary IP range of this new subnet cannot overlap the IP range of existing subnets in the current network, in peered VPC networks, or in on-premises networks connected via VPN or Interconnect.
You can optionally assign a secondary IP range to the subnet for use with Alias IP. The secondary IP range also cannot overlap the IP ranges of existing connected subnets.
CONSOLE GCLOUD
gcloud compute networks subnets create [SUBNET_NAME] — network [NETWORK] \
— range [IP_RANGE] \
[ — secondary-range [RANGE_NAME]=[2ND_IP_RANGE]
where
[SUBNET_NAME] is the name of the new subnet you are creating
[NETWORK] is the name of the existing network where you are creating the new subnet.
[IP_RANGE] is the primary IP range of the subnet. Example: 192.168.0.0/20.
[2ND_RANGE_NAME] is the name of the secondary IP range you can optionally create.
[2ND_IP_RANGE] is the range of the secondary IP range you can optionally create. Example: 172.16.0.0/16.
Expanding a CIDR block subnet to have more IP addresses
Expanding a subnet
You can expand the IP range of a subnet. You cannot shrink it.
Restrictions:
The new subnet must not overlap with other subnets in the same VPC network in any region.
The new subnet must stay inside the RFC 1918 address spaces.
The new network range must be larger than the original, which means the prefix length value must be a smaller number.
Auto mode subnets start with a /20 IP range. They can be expanded to a /16, but no larger.
gcloud compute networks subnets expand-ip-range [SUBNET_NAME] \
— region [REGION] \
— prefix-length [PREFIX_LENGTH]
[SUBNET_NAME] — the name of the subnet whose IP range you want to expand. You do not have to specify the network because the subnet and region together identify the network.
[REGION] — the region the subnet exists in.
[PREFIX_LENGTH] — the new numeric prefix length for the subnet. Must be smaller than the existing prefix length. For example, if the current subnet is a /24, the new prefix length must be 23 or smaller. This might change the first IP in the range. For example, if the original IP range was 10.128.131.0/24, specifying — prefix-length 20 sets the new IP range to 10.128.128.0/20.
Reserving static external or internal IP addresses
Reserving static external IP addresses
https://cloud.google.com/compute/docs/ip-addresses/reserve-static-external-ip-address
Reserving static internal IP addresses
https://cloud.google.com/compute/docs/ip-addresses/reserve-static-internal-ip-address
Working with management interfaces
Cloud Console
Cloud Shell
Cloud SDK
Monitoring and logging
Creating Stackdriver alerts based on resource metrics
https://cloud.google.com/monitoring/custom-metrics/creating-metrics
Choosing a monitored resource type
Each of your metric’s data points must include a monitored resource object. Points from different monitored resource objects are held in different time series.
You can use only the following monitored resource types in your custom metrics:
gce_instance Google Compute Engine instance.
gke_container Google Kubernetes Engine container.
dataflow_job Dataflow job.
aws_ec2_instance Amazon EC2 instance.
global Anything else.
A common practice is to use the monitored resource object that represents the physical resource where your application code is running. This has several advantages:
You get better performance.
You avoid out-of-order data caused by multiple instances writing to the same time series.
Your custom metric data can be grouped with other metric data from the same instance.
If none of the instance-related resource types are appropriate, use global. For example, Google App Engine users should use global because the resource type gae_app is not permitted in custom metrics.
Creating Stackdriver custom metrics
https://cloud.google.com/monitoring/custom-metrics/
https://cloud.google.com/monitoring/api/v3/metrics-details
Configuring log sinks to export logs to external systems
on premises
BigQuery
Viewing and filtering logs in Stackdriver
Viewing specific log message details in Stackdriver
Using cloud diagnostics to research an application issue
viewing Cloud Trace data
using Cloud Debug to view an application point-in-time
Viewing Google Cloud Platform status
Working with management interfaces
Cloud Console
Cloud Shell
Cloud SDK
Configuring access and security
Managing Identity and Access Management (IAM)
Viewing account IAM assignments
https://cloud.google.com/sdk/gcloud/reference/projects/get-iam-policy
https://cloud.google.com/sdk/gcloud/reference/organizations/get-iam-policy
Assigning IAM roles to accounts or Google Groups
https://cloud.google.com/sdk/gcloud/reference/projects/set-iam-policy
https://cloud.google.com/sdk/gcloud/reference/projects/add-iam-policy-binding
https://cloud.google.com/sdk/gcloud/reference/organizations/set-iam-policy
https://cloud.google.com/sdk/gcloud/reference/organizations/add-iam-policy-binding
Defining custom IAM roles
https://cloud.google.com/iam/docs/creating-custom-roles
https://cloud.google.com/sdk/gcloud/reference/iam/roles/
https://cloud.google.com/sdk/gcloud/reference/iam/roles/create
https://cloud.google.com/iam/reference/rest/v1/projects.roles
Managing service accounts
https://cloud.google.com/compute/docs/access/service-accounts
Managing service accounts with limited scopes
Best practices
In general, Google recommends that each instance that needs to call a Google API should run as a service account with the minimum permissions necessary for that instance to do its job. In practice, this means you should configure service accounts for your instances with the following process:
Create a new service account rather than using the Compute Engine default service account.
Grant IAM roles to that service account for only the resources that it needs.
Configure the instance to run as that service account.
Grant the instance the https://www.googleapis.com/auth/cloud-platform scope.
Avoid granting more access than necessary and regularly check your service account permissions to make sure they are up-to-date.
Assigning a service account to VM instances
https://cloud.google.com/compute/docs/access/create-enable-service-accounts-for-instances
Granting access to a service account in another project
Viewing audit logs for project and managed service
https://cloud.google.com/compute/docs/audit-logging
Cloud Audit Logging returns two types of logs:
Admin activity logs: Contains log entries for operations that modify the configuration or metadata of a Compute Engine resource. Any API call that modifies a resource such as creation, deletion, updating, or modifying a resource using a custom verb fall into this category.
Data access logs: Contains log entries for operations that perform read-only operations do not modify any data, such as get, list, and aggregated list methods. Unlike audit logs for other services, Compute Engine only has ADMIN_READ data access logs and do not generally offer DATA_READ and DATA_WRITE logs. This is because DATA_READ and DATA_WRITE logs are only used for services that store and manage user data such as Google Cloud Storage, Google Cloud Spanner, and Google Cloud SQL, which does not apply to Compute Engine. There is one exception to this rule: the instance.getSerialPortOutput does generate a DATA_READ log because the method reads data directly from the VM instance.
Ready Reference Commands (Hands-on Practice is important, this will be testified in the exam)
list the configurations on your system: gcloud config configurations list
create an new configuration gcloud config configurations create dev
Activate new configuration created gcloud config configurations activate dev
Set the account gcloud config set core/account user2@example.com
authorize the dev configuration. gcloud auth login
Display the active account name gcloud auth list
Display the active projects gcloud config list project
Set the zone gcloud config set compute/zone us-central1-b
Create containers gcloud container clusters create abctest
gcloud config set project <project name>
Display the OS image family names gcloud compute images list
Command should you use to deploy the application gcloud app deploy app.yaml
kubernetes Secrets Object is for passwords, OAuth tokens, and ssh keys #gcloud compute ssh
With underscores, you can connect the component & the groups or cmds #man gcloud_compute_instances_create
Command to update a deployment manager deployment #gcloud deployment-manager resources update
Edit the number of replicas in the YAML file and run the #kubectl set image command.
#gsutil signurl -d 10m
#man gcloud_compute_instances_create
#gcloud config unset compute/zone
#gcloud config set compute/zone us-east1-c
Fastest way to switch to the correct configuration #gcloud config configurations list followed by gcloud config configurations activate.
Cloud Run usecase is a service that adds, updates, deletes and lists addresses #gcloud config set run/platform managed #gcloud config set run/region REGION
Setup Cloud Billing #gcloud beta billing projects link PROJECT_ID –billing-account=ACCOUNT_ID [optional flags]
List off the existing components with: #gcloud components list
Install components with: #gcloud components install COMPONENT_ID
Remove components with: #gcloud components remove COMPONENT_ID
To view your quotas, use #gcloud compute project-info describe –project myproject command
#gcloud beta container clusters create $PRODUCT_CLUSTER_NAME
Pods can be created with # kubectl run or defined in YAML
Pods can be deployed with # kubectl apply
Applications are deployed with #gcloud app deploy app.yaml
Create and deploy a function with #gcloud functions deploy
Create a VPC #gcloud compute networks create command
Create a subnet #gcloud compute networks subnets create command
Create firewall rules #gcloud compute firewall-rules create command #gcloud compute firewall-rules create “allow-ssh” –network custom-dev-network
Start one or more instances with #gcloud compute instances start INSTANCE_NAMES command
Stop one or more instances with the #gcloud compute instances stop INSTANCE_NAMES command
Update an instance with the #gcloud compute instances update INSTANCE_NAME command
Delete one or more instances with the #gcloud compute instances delete INSTANCE_NAMES
Set region for the current configuration: #gcloud config set compute/region us-east4
Set zone for the current configuration: #gcloud config set compute/zone us-east4-c
Enterprise customers create the following 6 groups:
gcp-organization-admins
gcp-network-admins
gcp-security-admins
gcp-billing-admins
gcp-devops
gcp-developers
Reference: https://cloud.google.com/docs/enterprise/best-practices-for-enterprise-organizations
Global load balancing options:
• HTTP(S)
• SSL Proxy
• TCP Proxy
Regional load balancing options:
• Network TCP/UDP load balancing
• Internal TCP/UDP load balancing
Folder Hierarchy:
You can nest folders up to 10 (ten) levels deep.
A parent folder cannot contain more than 300 folders. This refers to direct child folders only. Those child folders can, in turn, contain additional folders or projects.
Final revision Tips (Should be used for revisioning only; 2–3 days before taking the exam)
Tips given below won’t exactly appear in the exam, however these notes helped to clear GCP ACE exam. All these points are available in above google cloud website link that i’ve captured over a period of time and have given for refreshing before going to the exam.
A Kubernetes concept that represents the smallest unit of deployment. Pod
App Engine traffic can be split by: IP address, Cookie, Random
Billing export formats. CSV file, JSON file, BigQuery
The command to enable an API. `gcloud services enable [ID]`
A `kubectl` flag that allows you to specify the JSON path of properties in JSON output. `-o` along with the `jsonpath` value. `kubectl get svc -o jsonpath`
Mounted directories that are accessible from inside containers. Volumes
A way to group different instances together. Unmanaged instance groups.
The command to update a Deployment Manager deployment. `gcloud deployment-manager deployments update`
Scaling modes supported by App Engine. Manual, Automatic, and Basic* *Only with standard environments
The database commonly paired with App Engine. Datastore
The purpose of this command:
`gcloud compute firewall-rules create “a-firewall-rule” — network $SERVICES_NETWORK — allow tcp:22`Open port 22 to the internet
A special account used for authenticating between different services. Service Accounts
When creating firewall rules, the lower the number the ______ the priority. Higher
Google’s horizontally scalable SQL database. Spanner
A mechanism that allows you to track custom information in code and save it to Stackdriver. Custom monitoring metric.
Name of a point-in-time backup of a persistent disk. Snapshots
The way to change an App Engine region. You can’t. You need to create a new project.
A feature of Cloud Shell that allows you to browse to port 8080? Web Preview
A service used for executing code in response to events? Cloud Functions
Flag to use when deploying to app engine that will prevent the version from getting 100% of the traffic? ` — no-promote`
The command to create a new Spanner database. `gcloud spanner databases create`
The fully managed platform that supports running web applications inside a Docker container. App Engine Flexible Environments
The name of the notation used for specifying IP address ranges. CIDR notation
Command to update a Kubernetes deployment that was created with the `kubectl create` command.`kubectl apply`
The types of App Engine environments. Standard and Flexible
Command to list Kubernetes services.`kubectl get svc`
Key-value pairs that you can set and interact with in a Compute Engine instance. Metadata
Types of available roles. Primitive roles, predefined roles, and custom roles.
The command to get Pod logs in Kubernetes.`kubectl get logs`
Key-value pairs of configuration data that are accessible from code running in a Cloud Function. Environment variables
The way to ensure the nodes in a Kubernetes Engine cluster are running the latest version of Kubernetes.Enable the “Automatic node upgrades” option.
The Cloud Storage metadata key to set to the MIME type. Content-Type
NoSQL’s realtime database.Firebase Realtime Database
The fully managed version of Redis.Cloud Memorystore
A sparsely populated database.Bigtable
The App Engine feature that allows fast rollbacks, A/B testing, and canary deployments.Traffic Splitting
The resource for storing sensitive information in Kubernetes.Secrets
The service that allows you to run a MySQL or Postgres database.Cloud SQL
The binary to interact with Cloud Storage.`gsutil`
The compute services provided by Google Cloud.Compute Engine, App Engine, Kubernetes Engine, and Cloud Functions.
The identity providers that Cloud IAM can use.G Suite, and Cloud Identity, Google Groups, Gmail accounts, Service Accounts
The format used for Kubernetes resource files.YAML
How to write to Stackdriver logs from a Cloud Function.Use the logging package or write to standard out.
A tool that warns you when you’re spending too much.Billing Alerts
Tool that exists in the Console allowing terminal access.Cloud Shell
A way to run Compute Engine instance based on templates.Managed Instance Groups
The command to list the current configuration for `gcloud`.`gcloud config list`
A Kubernetes resource that exposes deployments.Services
Any Database related questions is talking about Catalog then the answer could mostly be related to datastore
Big Query is priced in 2 ways. On-Demand, Flat rate. Storage is additional cost and no of queries on Demand
App engine pricing differs between standard and Flex versions
Kubernetes Engine application monitoring and logging is done at the cluster level
Default Stackdriver Logging for 30 days
Linking users to G Suite identities: Gmail, Google groups,Service accounts, GSuite users, Google Identity users
Project Roles to give to Auditors such as Org viewer, project viewer
Googles best practice is to create a group and then a role.
Create a ROLE for Auditors after you create a group and they will inherit the defined permissions. You can create and manage groups through the Admin Console.
If you just want to give a user the ability to connect to a virtual machine instance using SSH, but don’t want to grant them the ability to manage Compute Engine resources, add the user’s public key to the project, or add a user’s public key to a specific instance. You can avoid adding a user as a project member, while still granting them access to specific instances.
Signed URL’s allow read/write access to anyone who has the URL Service accounts authenticate with a key rather than a password. Like users and groups, service accounts can be assigned IAM roles to grant access to specific resources.
labels and tags are separate. If you create a label on an instance, Compute Engine does not create a tag for the instance. If you need to create a tag on an instance, you must create the tag manually.
App Engine is regional, You cannot change an app’s region after you set it
SSH keys are set as either a project or instance metadata
You can set alerts based on a percentage of your monthly budget
Set up billing exports to estimate daily/monthly charges
Export formats are: File (CSV, JSON) & BigQuery
With Self-serve billing, you pay when you hit the billing threshold or every 30 days; whichever happens first.
Cloud SQL is used when you need a traditional SQL database
Spanner is used when you need a traditional SQL database that can scale horizontally
Bigtable is a sparse table, used when you have massive amounts of keyed data
BigQuery is a data warehouse service that can query massive data sets quickly
Datastore is a NoSQL database built on top of Bigtable
Final revision Tips (1 day before taking the exam)
https://cloud.google.com/certification/practice-exam/cloud-engineer
NOTE: If you’re unable to answer the questions in practice exam, reschedule the exam and start concentrating on lagging areas.