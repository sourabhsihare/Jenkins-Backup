pipeline{
    agent any
    stages{
        stage("Backing up Primary server"){
            steps{
                echo "Taking backup of Primary server"
                // Replace IP address with hostname of your environment
                sh 'rsync -a jenkins@192.168.56.15:/var/lib/jenkins /var/lib/jenkins_primary_server_backup'
                              
            }
        }
    }
}
