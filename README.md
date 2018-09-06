#EOS NODE
- INSTALL EOS NODE:

ansible-playbook -i hosts  ./eosnode.yml  --tags installEos

- BACKUP EOS NODE:  

ansible-playbook -i hosts  ./eosnode.yml  --tags backupEos

- EXAMPLE main.yml in vars

mainnet_version: 1.2.3  
eos_git_repo: "https://github.com/EOS-Mainnet/eos.git"  
eos_source_dir: /home/eos-sources  
eosdir: /opt/EOSmainNet - datadir EOS  
backup_dir: Path to local backup dir  
remote_backup_dir: Path to dir on backup server  
ipnode: "IP address backup server"  
remote_copy: "1"  
sudopass: "password"  
