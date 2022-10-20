# Ansible Playbook: Install Elasticsearch (Debian)

With this playbook you can install and configure your first Elastischsearch cluster.
This is playbook is pure for first usage as it will also install snmp and java on the machine.
The supported operating system is all the system that are debian based (as we suggest the use of Ubuntu).

The playbook should be executed with elevated rights as some super user actions are needed for the installation.

Note: installed version of elassticsearch is version 6.8.

Before running the playbook some variables need to be set in the variables.yml file.

## Before running the playbook

### Copy files

Copy all the files to the following location:
/home/ansible/install_elastic

If the location doesn't exist, you can easily create it.

### Change the needed variables

In the variable folder, you'll find the variables.yaml file. Here you will need to change the following variables:
- clustername: set a custom clustername if wanted 
- discovery : add all the ip addresses that you want in the elasticsearch cluster (these should be the same as in the ansible hosts file)
- masternodes: calculate the amount of masternodes with: (nodes/2)+1 and fill in the number
- xmsram: set value for Xms as followed Xmsxg where second x = memory/2 (eg: Xms8g)
- xmsram: set value for  Xmx as followed Xmxxg where third x = memory/2 (eg: Xmx8g)

### Ansible hosts file

The playbook is configured to run all the hosts from [elastic]. You can change this in the ansible hosts file, or change the hosts in the playbook.

## Running the playbook

Once everything is configured you can run the playbook with:
```bash
ansible-playbook installElastic.yaml --ask-become-pass
```

## License

Code and documentation in this project are released under the [MIT License](https://github.com/SkylineCommunications/Skyline-DataMiner-Deploy-Action/blob/feature/preRelease/LICENSE.txt). 
