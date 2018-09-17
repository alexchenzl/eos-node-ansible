#EOS NODE ANSIBLE  
- PREPARE FOR INSTALLATION USING ANSIBLE  

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

ansible-playbook -i hosts  ./eosnode.yml  --tags configEos  
or  
ansible-playbook -i hosts -l 192.168.1.12 ./eosnode.yml  --tags configEos  
for a single host  

- EXAMPLE main.yml in vars directory

branch: master  
eos_git_repo: "https://github.com/EOSIO/eos.git"  
eos_source_dir: /home/eos-sources   -  directory with source code  
eos_dir: /opt/EOSmainNet    - datadir EOS  
nodeos_bin_dir: /home/eos-sources/build/programs  -  dir of binary files nodeos  
backup_dir: /Path/to/local/backup/dir  
remote_backup_dir: Path/to/remote/dir/on/backup/server  
ipnode: "182.66.11.11" IP address of backup server  
remote_copy: "1"  
sudopass: "password"  
nodes_type: "full"  The nodes types must be "full" or "seed"  
newline: "\n"  


- Use compilation log on host which to install EOS  
tail -f /home/eos-sources/install.log.txt   
