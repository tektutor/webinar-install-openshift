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
![image](https://github.com/user-attachments/assets/b8b8c810-b33e-47f5-97f0-044928304a22)

When we click on "Install Openshift on your laptop", we get the below page
![image](https://github.com/user-attachments/assets/46a34b30-09fe-469b-9235-82b0c906655e)

Make sure you donwload the crc-linux-amd64.tar.xz or appropriate installer for your OS.  The pull-secret is required to download the necessary tools and container images while installing Openshift and after installing openshift as well.

Red Hat will be able to track your usage based on the pull-secret.
![image](https://github.com/user-attachments/assets/fd8d9b19-1c6a-4391-90e6-000c9d3b21f5)

Let's extract and copy the crc binary to /usr/local/bin as admin user
```
cd ~/Downloads
ls
tar xvf crc-linux-amd64.tar.xz
ls
cd crc-linux-2.45.0-amd64/
sudo cp crc /usr/local/bin
ls -l /usr/local/bin/crc
```
![image](https://github.com/user-attachments/assets/587c53c9-82f3-477c-ade5-a2d1f1f927d0)

Let's configure RAM and CPUs for Openshift
```
crc config set memory 32768
crc config set cpus 8
```
![image](https://github.com/user-attachments/assets/343e2f39-cded-4f89-a8c9-ffcee6cf56c7)


