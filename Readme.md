##Topics: archiving, sshkey creating,downloading(fetch), sending, creating user,modifying visudo.
***So here is my first project. Not very clean and optimized, but usable. ***

1. First you need to configure hosts.ini file, add some information to connect to your servers.
2. Run main.yml  $ ansible-playbook -i hosts.ini main.yml (it should create ansible users)
3. Then run sshkeygen.yml to create ssh keys and folder.
4. then you can run main.yml again but uncomment "archiving" role. 
5. Now you can use "crontab -e" to create cronjob on master ansible node:
       crontab -e
       * */12 * * * ansible-playbook -i /home/ansible/project1/hosts.ini /home/ansible/project1/main.yml
   Result: now it should run archiving role at 12AM and 12PM.

6. to remove cronjob use: 
	crontab -r
   to see cronjobs
	crontab -l 
   
