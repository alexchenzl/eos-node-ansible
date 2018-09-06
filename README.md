#EOS NODE
- INSTALL EOS NODE:

ansible-playbook -i hosts  ./eosnode.yml  --tags installEos

- BACKUP EOS NODE:  

ansible-playbook -i hosts  ./eosnode.yml  --tags backupEos

