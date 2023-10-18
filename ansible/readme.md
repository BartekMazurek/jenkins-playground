## Job with ansible playbook

***

#### 1 - Check ansible connection between jenkins host & remote host (server name defined in ansible inventory)
> ansible -i <HOSTS_FILE> -m ping <SERVER_NAME>

#### 2 - Run ansible playbook yml file
> ansible-playbook -i <HOST_FILE> <PLAYBOOK NAME>