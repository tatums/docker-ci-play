## HACK - continuous delivery


## sources


https://serversforhackers.com/getting-started-with-docker

https://docs.docker.com/compose/rails/


## init
```
ansible-playbook -i hosts playbooks/development/00-init.yml
```

## pull code
```
ansible-playbook -i hosts playbooks/development/01-code.yml
```

## build
```
ansible-playbook -i hosts playbooks/development/02-build.yml
```

## run
```
ansible-playbook -i hosts playbooks/development/03-run.yml
```

## NOTES

If you destroy a vagrant image then rebuild.  You may see this error.
```
GATHERING FACTS ***************************************************************
fatal: [192.168.33.11] => SSH Error: Host key verification failed.
    while connecting to 192.168.33.11:22
It is sometimes useful to re-run the command using -vvvv, which prints SSH debug output to help diagnose the issue.
```

This happens because the old host is stored in the known_hosts file
```
The authenticity of host '192.168.33.11 (192.168.33.11)' can't be established.
RSA key fingerprint is 77:9d:6c:94:11:60:08:ff:86:d1:e6:7e:cc:66:c3:cb.
Are you sure you want to continue connecting (yes/no)? yes
```
open up known_hosts file and remove the old server entry
vim ~/.ssh/known_hosts

