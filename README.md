#EOS NODE
- INSTALL EOS NODE:

ansible-playbook -i hosts  ./eosnode.yml  --tags installEos

- BACKUP EOS NODE:  

ansible-playbook -i hosts  ./eosnode.yml  --tags backupEos

- EXAMPLE main.yml in vars directory

mainnet_version: mainnet-1.2.3  
eos_git_repo: "https://github.com/CryptoLions/EOS-MainNet.git"  
eos_source_dir: /home/eos-sources   -  directory with source code  
eosdir: /opt/EOSmainNet    - datadir EOS  
backup_dir: /Path/to/local/backup/dir  
remote_backup_dir: Path/to/remote/dir/on/backup/server  
ipnode: "182.66.11.11" IP address of backup server  
remote_copy: "1"  
sudopass: "password"  
