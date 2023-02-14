pipeline{
    agent any
    stages{
        stage("Copy files to Docker Server"){ 
            steps{
                script{
                    sshagent(['sshCredentials']) {
                        sh 'pwd'
                        sh 'ssh -t -o StrictHostKeyChecking=no ubuntu@35.183.109.118'
                        sh 'scp classproject/Google-Kubernetes-boilerplate/app/adservice/* ubuntu@35.183.109.118:~/'
                        sh 'scp dockerinstallscript.sh ubuntu@35.183.109.118:~/'
                    }    
                }
            }
        }
    }
}

    
