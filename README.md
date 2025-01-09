# webinar-install-openshift

## Openshift Installation
There are many options
<pre>
1. Installing Managed Red Hat Openshift in AWS ( ROSA ) 
2. Installing Managed Red Hat Openshift in Azure ( ARO )
3. Installing Red Hat Openshift in local system ( baremetal, on-prem, private cloud )
</pre>

## Managed Red Hat Openshift in AWS (ROSA)
<pre>
- Managed openshift Sofware as a Service ( Saas )
- For any technical issues AWS(Amazon) will provide support to your organization
- AWS manages all the master nodes, they decide the configuration of the master nodes
- We have a choice to decide the number of worker nodes, even to some extent we can control the worker node configuration
- Pretty expensive, but very stable
</pre>

## Managed Red Hat Openshift in Azure (ARO)
<pre>
- Managed openshift Sofware as a Service ( Saas )
- For any technical issues Azure(Microsoft) will provide support to your organization
- AWS manages all the master nodes, they decide the configuration of the master nodes
- We have a choice to decide the number of worker nodes, even to some extent we can control the worker node configuration
- Slightly cheaper compared to AWS
</pre>

## Red Hat Openshift OS supported by Master and Worker Node
<pre>
- Until Openshift 3.11, we can install RHEL or any other Linux OS[RHEL] distribution in master and worker nodes
- Starting from Openshift 4.x, we can only install Red Hat Enterprise Core OS (RHCOS) in master nodes
- In worker nodes, we could choose between RHEL or RHCOS
- Red Hat recommends using RHCOS in master and worker nodes
- When we install RHCOS in master and worker nodes, we can upgrade Openshift using webconsole or oc command
- RHCOS
  - is an optimized OS which is created out of RHEL, optimized for container orchestration platforms
  - it comes with pre-installed Podman and CRI-O container runtime
  - it enforces many best practices
  - if the best practices are not followed, simply many things won't work
  - Ports below 1024 are reserved for openshift's internal use, user applications can't use these ports
  - Many OS folders are given only read-only permission, writing to such folder will lead to Pod crash
  - All the user applications are allowed only to run as non-admin user
</pre>

## Installing Red Hat Openshift in local server
<pre>
- is the tough compared to installing in public cloud ( production grade setup )
- openshift local is the easiest of all, this is what we are going to do
</pre>

## How to install Openshift in local machine ( non-production setup ) with Code Ready Containers[CRC]
<pre>
- We need Red Hat Developer account which is free
- It doesn't require credit card
- With Red Hat Developer account we can evaluate free of cost
  - Red Hat Enterprise Linux 
  - Red Hat Ansible Tower ( called Ansible Automation Platform )
  - or other Red Hat products
- just your gmail is enough to create a free red hat developer account
</pre>

We need to login to red hat developer account
<pre>
https://developers.redhat.com/  
</pre>

![image](https://github.com/user-attachments/assets/d731bc10-08a7-453c-8463-391f750065b4)

Navigate to the below URL to download CRC and pull-secret file
<pre>
https://developers.redhat.com/products/openshift-local/getting-started  
</pre>
