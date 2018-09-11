#EOS NODE
- INSTALL EOS NODE:

ansible-playbook -i hosts  ./eosnode.yml  --tags installEos

- BACKUP EOS NODE:  

ansible-playbook -i hosts  ./eosnode.yml  --tags backupEos

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
