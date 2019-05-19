# SSHKEYS manager
Add and revoque ssh keys dinamically from remote servers

## Steps
1) Move vars/userslist.yml.example to vars/userslist.yml 
2) Fill the var "all_users_list" with your users list and their ssh keys (they can have multiples).

## How to use
The best way is leaving empty allowed_users and revoqued_users and call the playbook with --extra-vars
To add users keys to remote servers:
`ansible-playbook main.yml --extra-vars "allowed_users=User1,User2,User44"`
To remove users keys from remote servers:
`ansible-playbook main.yml --extra-vars "revoqued_users=User1,User2,User44"`

###Rundeck Integration
To use this script with rundeck, you can create a Job, with 3 options:
* remote_user: The remote user which will have the keys
* add_users: Those users which will have their keys added
* revoque_user: ONLY ONE, which user will have their key revoqued

and call playbook with the next syntax:
 --extra-vars "{"users": remote_user=${remote_user} allowed_users:${option.add_users} revoqued_users:${option.revoque_user}"}
