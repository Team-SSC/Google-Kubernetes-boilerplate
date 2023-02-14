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
                        sh 'scp -r $WORKSPACE/TeamSCC-project/ ubuntu@35.183.109.118:~/'
                        sh 'sudo chmod 777 dockerinstallscript.sh'
                        sh 'sh dockerinstallscript.sh'
                        sh 'docker build -t adserviceshyne'
                        
                    }    
                }
            }
        }
    }
}

    
