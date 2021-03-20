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
**Note**: Above steps are required to establish password less connection from scecondary to primary server

5) Create backup directory on secondary server where you want to keep the primary Jenkins data and change the user permision to jenkins user with below commands:

        sudo mkdir /var/lib/jenkins_primary_server_backup
   
        chown -R jenkins:jenkins /var/lib/jenkins_primary_server_backup/

#How Take Backup

1) Create Jenkins Pipeline job from this repository
2) Build the job


#Failure Recovery Steps

1) Rename the backup directory on the secondary server from /var/lib/jenkins_primary_server_backup to /var/lib/jenkins

2) Restart seconadary server
        
        
        
        
