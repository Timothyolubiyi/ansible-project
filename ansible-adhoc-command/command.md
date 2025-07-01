### check for the list of items on the target machines
ansible -i inventory all -a "ls"
### check for the list of items and hidden files on the target machines
ansible -i inventory all -a "ls -lart"
### now create directory templates on all machines
ansible -i inventory all -a "mkdir templates"
### To remove cloud folder
ansible -i inventory all -a "rm -r -f cloud"
### ### To check the disk/memory space on all hosts in an inventory file
ansible -i inventory all -m shell -a 'df -h'
### To find ids on host machines
ansible -i inventory webservers -m shell -a 'id'
OR
ansible -i inventory all -m shell -a 'id'
### ansible ad hoc command to check the free memory or memory usage of hosts
ansible -i inventory all -a "free -m"

### first create a file touch /tmp/my-file.txt on the control server and push it to all #machines
touch /tmp/my-file.txt
### to copy to anther server
ansible -i inventory webservers -m copy -a "src=/tmp/my-file.txt dest=/tmp/my-file.txt"

##  to install apache on all machines
ansible -i inventory webservers -m apt -a 'name=apache2 state=latest'