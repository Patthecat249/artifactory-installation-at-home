# artifactory-installation-at-home

# Requirements
- VM mit Rocky, RHEL, Fedora or CentOS
- Internet-Access
- Downloaded JFrog Testversion

# Steps
- Install VM
- Download some tools JFrog-Binaries
- Create SSL-Key & Certificate
- Install artifactory
- Configure Jfrog 

# Execute Playbook to Install and Configure Artifactory
```bash
# Execute on Localhost, where you cloned the Repository
mkdir git && cd git && git clone https://github.com/Patthecat249/artifactory-installation-at-home.git
cd artifactory-installation-at-home/ansible/ && ansible-playbook 01-install-artifactory.yaml
```

# Post-Tasks
- Check, if nginx is configured correctly in Artifactory
  - Go to: Administration > Services JFrog Container Registry > HTTP Settings
  - Check if Docker Access Method="Sub Domain" is configured
    - SSL Key Path: /jfrog/ssl-certs/wildcard-artifactory-key.pem
    - SSL Certificate Path: /jfrog/ssl-certs/wildcard-artifactory-crt.pem
- Update Admin-Password or Create a new User
- Create a local Repository named "openshift"
- Try to login to the new repo from CLI with: `podman login openshift.artifactory.home.local -u admin -p <password>` 
- Mirror OpenShift-Content to local Repository by using oc-mirror
  - Execute `ansible-playbook 02-mirror-openshift-content-to-registry.yaml`
