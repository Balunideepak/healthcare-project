install all the required packesgs
- docker = sudp apt install docker.io -y 
- anisble = https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-ubuntu-20-04
- k8s = https://github.com/Balunideepak/Deployment-script.git
- jenkins = https://github.com/Balunideepak/Deployment-script.git
- Set the environment varibale in ~/.bashrc file after updation restart restart "source ~/.bashrc" file 
- give Jenking permission to access docker  :  usermod -aG docker jenkins
- update visudo file to all jenking to bypass password "jenkins ALL=(ALL:ALL) NOPASSWD: ALL" 
_________________________________________________________________________________________________________________________________
  After login in Jenkins :
___________________________________________________________________________________________
Add credintials :- 
  - docker hub login ( make sure your ID match the id in jenkinsfile)
  - ssh key (make sure your ID match the id in jenkinsfile)
 ___________________________________________________________________________________________________
 Add tools :-
 - the environment variable you set in ec2 machine.
 - like JAVA_HOME, M2_HOME , ANSIBLE
____________________________________________________________________________________________________
* install plugins : docker, pipeline, prometheus,html publisher,
* restart the jenkins : service jenkins restart
________________________________________________________________________________________________
* build item :-
    - slelect git  --> add repository https://github.com/Balunideepak/healthcare-project.git   --> select deepjenkinsfile --> save --> build now.
_____________________________________________________________________________________
* in master node run folling command.
  - kubectkl get pods -o wide
  - kubectl  get svc -o wide
______________________________________________________________________________________
* copy the <Public IP of the node machine: NodePort no which you got in "kubectl  get svc -o wide" command> and see you websit is working.
______________________________________________________________________________________________________________________________ :D :D :D _________________
for monitoring....
prometheus link: sudo su wget https://github.com/prometheus/prometheus/releases/download/v3.2.1/prometheus-3.2.1.linux-amd64.tar.gz 
	

grafana link : wget https://dl.grafana.com/enterprise/release/grafana-enterprise-8.4.4.linux-amd64.tar.gz
