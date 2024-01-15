Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

## SELinux Artifactory

### sudo
`sealert -l ffe57c29-c9e3-4ad1-b7e7-f1ca373e9843`
```bash
ausearch -c 'su' --raw | audit2allow -M my-su
semodule -i my-su.pp
```
### Artifactory Start-Script
`sealert -l 2cca6e43-7d70-4d4e-b365-eaf2a0c8aea7`
```bash
ausearch -c 'artifactoryMana' --raw | audit2allow -M my-artifactoryMana    
semodule -i my-artifactoryMana.pp
```
### Artifactory Java
`sealert -l d4a9dd84-9d26-490b-a680-9549eec2e92b`
```bash
ausearch -c 'java' --raw | audit2allow -M my-java
semodule -i my-java.pp
```
### Artifactory YQ
`sealert -l ccb53c3d-7fb4-4f9b-96e2-756a819cb7dd`
```bash 
ausearch -c 'yq' --raw | audit2allow -M my-yq
semodule -i my-yq.pp
```
### NGINX Port 8082
`sealert -l 4d95a0ba-6124-4174-814b-1dd1722a6485`
```bash
ausearch -c 'nginx' --raw | audit2allow -M my-nginx
semodule -i my-nginx.pp
```
Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
