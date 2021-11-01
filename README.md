# Ansible - Weight Tracker Deployment on Azure Cloud VMs.

### This repo you will find:
* Weight Tracker app deployed with ansible, using roles, variables and different modules.
* YAML to write ansible configurations.
* A controller machine which deploy the app to different enviroments (staging and production) using a single playbook.

## How to use
**If you want the Weight Tracker App to be deployed on your machine, follow the next steps:**
1. Make sure you have all the prerequisites to use ansible (linux machines only have the ability to run ansible). Use this: [Installation Guide](https://adamtheautomator.com/install-ansible/)
3. Clone this repo to your host machine (the controller), or open a new YAML file and paste the configuration.
4. Navigate to /etc/ansible/ and edit the hosts file. In the hosts file you can define your working groups, such as "test" or "production" and assign to each group their unique properties. Here we will just store there the IPs of the relevant machines. 
create your groups like this:

![Hosts file](https://image.slidesharecdn.com/ansibledcmeetup20150108-150108212710-conversion-gate01/95/using-ansible-dynamic-inventory-with-amazon-ec2-6-638.jpg?cb=1420774103)

   Group name inserted "[]", and below that the machines ip.

5. Make a new directory called "group_vars" in the same directory where you have the playbook and create a YAML file there with the same name as your group name (enviroment name)
6. Make sure your enviroments are ready and run the playbook with this command:
*  Ansible-Playbook *Your Play book YAML file* --extra-vars "group=*your group name* var_file_path=*group_vars/variable file name*"
