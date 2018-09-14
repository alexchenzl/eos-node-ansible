#EOS NODE ANSIBLE  
- PREPARE FOR INSTALLATION USING ANSIBLE  

For normal operation of the ansible, you must add id_rsa.pub key to authorized_keys on host and add lines "User_Alias  ADMINS = eosuser" and "ADMINS  ALL = NOPASSWD: ALL" to file /etc/sudoers  

- INSTALL EOS NODE:

ansible-playbook -i hosts  ./eosnode.yml  --tags installEos  
or  
ansible-playbook -i hosts -l 192.168.1.12 ./eosnode.yml  --tags installEos  
for a single host  

- INSTALL EOS RUN/STOP SCRIPTS AND MAKE DATADIR:

ansible-playbook -i hosts  ./eosnode.yml  --tags installEosRunner  
or  
ansible-playbook -i hosts -l 192.168.1.12 ./eosnode.yml  --tags installEosRunner  
for a single host  

- BACKUP EOS NODE:  

ansible-playbook -i hosts  ./eosnode.yml  --tags backupEos  
or  
ansible-playbook -i hosts -l 192.168.1.12 ./eosnode.yml  --tags backupEos  
for a single host  

- CONFIGURE EOS NODE

To configure Eos node you must create "templates" directory in the "eosnode" directory and create config.ini.j2 file in it.  
config.ini.j2 file is a config.ini file containing the following lines:    
{% if nodes_type == 'full' %}  
    filter-on = *{{ newline }}{{ newline }}  
{% elif nodes_type == 'seed' %}  
    #filter-on = {{ newline }}{{ newline }}  
{% endif %}   
finally enter the following command  
ansible-playbook -i hosts  ./eosnode.yml  --tags configEos  
or  
ansible-playbook -i hosts -l 192.168.1.12 ./eosnode.yml  --tags configEos  
for a single host  

- EXAMPLE main.yml in vars directory

branch: master  
eos_git_repo: "https://github.com/EOSIO/eos.git"  
eos_source_dir: /home/eos-sources   -  directory with source code  
eosdir: /opt/EOSmainNet    - datadir EOS  
backup_dir: /Path/to/local/backup/dir  
remote_backup_dir: Path/to/remote/dir/on/backup/server  
ipnode: "182.66.11.11" IP address of backup server  
remote_copy: "1"  
sudopass: "password"  
nodes_type: "full"  The nodes types must be "full" or "seed"  
newline: "\n"  


- Use compilation log on host which to install EOS  
tail -f /home/eos-sources/install.log.txt   
