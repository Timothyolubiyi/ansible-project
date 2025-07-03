#To start server
ansible-playbook -i inventory start-nginx.yml

#To confirm 
sudo systemctl status nginx
#To stop Server
ansible-playbook -i inventory stop-nginx.yml
