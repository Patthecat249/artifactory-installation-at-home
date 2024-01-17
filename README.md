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