				
													Lab: install/delete Jenkins by Ansible

Create Ansible roles for installing Jenkins – 3  
tune sysctl parameters for VM:  
vm.min_free_kbytes  
fs.file-max = 2097152  
net.core.somaxconn = 65000  
disable swap  
disable THP  
install openjdk-11-jdk  
Jenkins should be enabled on startup  
setup custom port 8081 for Jenkins  
install plugins: GitHub, Role-based authorization strategy, NodeJS  
add new user – Jenkins-NAME(your fullname, Jenkins-linustorvalds)  
Create separate role for deleting Jenkins - 3  
delete all components related to the Jenkins including openjdk-11-jdk  
state of the should be the same as before installation Jenkins  
the parameters of VM configured before can remain the same  
Configure Nginx reverse proxy for Jenkins - 2  
Nginx config should be located in Jenkins install role  
don’t forget to delete Nginx in Jenkins delete role!!!  
Add separated playbooks “jenkins-setup.yml”, “jenkins-cleanup.yml” adding Jenkins roles which were created before.   
  Create playbook with name “setup_jenkins_environment.yml” and import “jenkins-setup.yml”, “jenkins-cleanup.yml” into this playbook also adding “tags” to distinguish. – 1  
Add inventory file with your VM.  
* Spin up and connect Jenkins-agent in Docker. Describe it in “install-jenkins” role.  
  
Notes: please use Ansible native modules as much as possible, avoid using “shell” module  

Results:  

Create separated directory in https://stash.playtika.com/projects/IA/repos/ansible/browse repo with name “ansible_domainName”, for example “ansible_ipysmennyi”. All code should be created in feature branch with name “feature/domainName”, for example “feature/ipysmennyi”. After merge to “master” branch.  
