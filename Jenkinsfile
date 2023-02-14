pipeline{
    agent any
    stages{
        stage("Copy files to Docker Server"){ 
            steps{
                script{
                    sshagent(['sshCredentials']) {
                        sh 'pwd'
                        sh 'ls'
                        sh 'df -h'
                        sh 'ssh -t -o StrictHostKeyChecking=no ubuntu@35.183.109.118'
                        sh 'scp -r /var/jenkins_home/workspace/TeamSCC-project ubuntu@35.183.109.118:~/'               
                        sh 'touch testfile.txt'
                        sh 'chmod 777 TeamSCC-project/dockerinstallscript.sh'
                        sh 'sh TeamSCC-project/dockerinstallscript.sh'
                        sh 'docker build -t adserviceshyne'
                        
                    }    
                }
            }
        }
    }
}

    
