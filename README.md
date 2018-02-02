# ans_setup_jenkins
Ansible recipe for Jenkins deployment on fresh Debian install

This ansible recipe makes use of Geerlinguy's fantastic ansible recipe :
https://github.com/geerlingguy/ansible-role-jenkins/

And updates it to support Jenkins 2.102, plugin installation using install-plugins.sh script from Jenkins' Docker install repo.
Remote CLI is disabled at install, you can enable it by setting it in jenkins.CLI.xml to enabled.

!!WARNING!! This recipe is intended to replicate settings of a previously properly configured Jenkins, and requires :
  - /etc/ssl/certs/java/cacerts
  - ${JENKINS_HOME}/secrets/hudson.util.Secret
  - ${JENKINS_HOME}/secrets/master.key
  - ${JENKINS_HOME}/config.xml

This is for the portability of the LDAP manager password secret. 
OF COURSE THOSE ARE NOT INCLUDED IN THIS REPO AND SHOULD NEVER BE SHARED.

!!WARNING!! Agent to Master security has to be enabled manually, as I was not (yet) able to find the file to change.

Working install with a KVM preseeded with Debian9, root SSH login configured via SSH public key and Ansible 2.4.3.0 and using
the '-u root' flag.
