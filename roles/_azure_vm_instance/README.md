instances_to_group
=========
Adds targeted hosts to groups

Requirements
------------
none

Role Variables
--------------
* ``filter_name``: Name tag filter; 
  Default: `"*"`
* ``filter_role``: Role tag filter;
  Default: `"*"`
* filter_instance_id: Instance ID filter;
  Default: `"*"`
* ``filter_instance_state``: Instance state filter;
  Default: `"running"`
* ``filter_tags``: Additional tags to filter by;
  Default: `[]`
* ``cloud_filters``: List of filters that will be used;
  Default: `[]`
* ``connect_via_public``: Determines whether the connection to the instance will be made on the public or private IP;
  Default: `false`
* ``use_domain``: Determines whether the instances are domain joined;
  Default: `false`
* ``override_get_all``: Override for getting all instances, USE WITH CAUTION;
  Default: `false`
* ``include_ip_in_hostname``: Adds the IP address of the instance to the hostname, used for autoscale instances;
  Default: `true`
* ``base_user``: User for ssh_key_dir;
  Default: `ec2-user`
* ``ssh_key_dir``: Directory where key pairs live;
  Default: `/home/{{ base_user }}/.ssh`

Dependencies
------------
none

Example Playbook
----------------
    - role: instances_to_group
      filter_name: "{{ name | default('*') }}"
      filter_role: "domaincontroller"
      filter_instance_id: "{{ instance_id | default('*') }}"
      target_group: domain_controllers

License
-------
All Rights Reserved

Author Information
------------------
ShareFile SREs