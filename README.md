Create_Inventory_with_Ansible
=========

This role is used to create inventory file from the list of target nodes. Which can be directly imported into Xcel Sheets. Contains the details of the form:

![alt text](https://github.com/akhan4u/Create_Inventory_with_Ansible/blob/master/AnsibleInventory.png)


Requirements
------------

1. We need Ansible software to be installed in order to use these roles, means Roles can be run from any machine that have Ansible installed on.

Here are the steps to install the Ansible on Ubuntu 14.04 LTS:

	sudo apt-add-repository -y ppa:ansible/ansible  
	sudo apt-get update  
	sudo apt-get install -y ansible


2. Requires 'gather_facts' to be set to 'yes' to collect the various facts about the system for generating the inventory.

Role Variables
--------------

1. Specify the location where to create the inventory file.
	      
	         inventory_location: /data

2. Specify the name of the inventory file to be created

	        inventory_filename: Inventory
Dependencies
------------

None

Example Playbook
----------------

Sample playbook leveraging this role:

  	- hosts: "{{ host_name }}"
    	  gather_facts: yes
      	  become: true
    	  tags: inventory
    	  vars:
      	    - inventory_location: /data
              inventory_filename: Inventory
    	  roles:
      	    - Create_Inventory_with_Ansible


License
-------

BSD

Author Information
------------------

Amaan Khan  
Email: Amaan.ngp@gmail.com  
LinkedIN: https://www.linkedin.com/in/amaan-khan-linux-ninja/  
Twitter: @Amaankhan4you  
