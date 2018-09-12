#EOS NODE ANSIBLE  
- PREPARE FOR INSTALLATION USING ANSIBLE  

For normal operation of the ansible, you must add id_rsa.pub key to authorized_keys on host and add lines "User_Alias  ADMINS = eosuser" and "ADMINS  ALL = NOPASSWD: ALL" to file /etc/sudoers  

- INSTALL EOS NODE:

ansible-playbook -i hosts  ./eosnode.yml  --tags installEos  
or  
ansible-playbook -i hosts -l 192.168.1.12 ./eosnode.yml  --tags installEos  
for a single host  

- BACKUP EOS NODE:  

ansible-playbook -i hosts  ./eosnode.yml  --tags backupEos  
or  
ansible-playbook -i hosts -l 192.168.1.12 ./eosnode.yml  --tags backupEos  
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

- Use compilation log on host which to install EOS  
tail -f /home/eos-sources/install.log.txt   
