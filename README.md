### EOS NODE ANSIBLE   

### INSTALL EOS NODE:

$ ansible-playbook -i hosts  ./eosnode.yml  --tags installEos  
or  
$ ansible-playbook -i hosts -l 192.168.1.12 ./eosnode.yml  --tags installEos  
for a single host  

### INSTALL EOS RUN/STOP SCRIPTS AND MAKE DATADIR:

$ ansible-playbook -i hosts  ./eosnode.yml  --tags installEosRunner  
or  
$ ansible-playbook -i hosts -l 192.168.1.12 ./eosnode.yml  --tags installEosRunner  
for a single host   

### BACKUP EOS NODE:  

$ ansible-playbook -i hosts  ./eosnode.yml  --tags backupEos  
or  
$ ansible-playbook -i hosts -l 192.168.1.12 ./eosnode.yml  --tags backupEos  
for a single host  

### CONFIGURE EOS NODE

$ ansible-playbook -i hosts  ./eosnode.yml  --tags configEos  
or  
$ ansible-playbook -i hosts -l 192.168.1.12 ./eosnode.yml  --tags configEos  
for a single host  

### Use compilation log on host which to install EOS  
tail -f /home/eos-sources/install.log.txt   
