# ansible settings

ssh-keygen -t rsa -b 4096 -C "charsyam"
ansible all -m copy -a "src=/home/user/.ssh/id_rsa.pub dest=/tmp/id_rsa.pub" --ask-pass -c paramiko
ansible all -m shell -a "mkdir -p /home/charsyam/.ssh/" --ask-pass -c paramiko
ansible all -m shell -a "cat /tmp/id_rsa.pub >> /home/charsyam/.ssh/authorized_keys" --ask-pass -c paramiko
