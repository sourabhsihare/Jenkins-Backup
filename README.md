## Jenkins-Backup
#Take backup of Primary instance of Jenkins to Secondary instance

##Prerequsite 

We should have the ssh connectivity between these two servers

 1) Login to secondary master server and switch to user with which Jenkins is running 
 2) Generate the ssh key pair using below command 
       
       ssh-keygen -b 4096
       
 3) Use ssh-copy-id command to copy the public key to primary jenkins server, use below command:

       sh-copy-id jenkins@jenkins-host-name
       
4) Now check if you can ssh from primary server to secondary server using ssh without password

        ssh jenkins@jenkins-primary-server
