pipeline{
    agent any
    stages{
        stage("Copy files to Docker Server"){ 
            steps{
                script{
                    sshagent(['sshCredentials']) {
                        sh 'pwd'
                        sh 'ls'
                        sh 'ssh -t -o StrictHostKeyChecking=no ubuntu@35.183.109.118'
                        sh 'scp $WORKSPACE/* ubuntu@35.183.109.118:~/'
                        sh 'scp dockerinstallscript.sh ubuntu@35.183.109.118:~/'
                    }    
                }
            }
        }
    }
}

    
