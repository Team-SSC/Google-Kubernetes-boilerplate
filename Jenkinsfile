pipeline{
    agent any
    stages{
        stage("Copy files to Docker Server"){ 
            steps{
                script{
                    sshagent(['sshCredentials']) {
                        sh 'pwd'
                        sh 'scp /Users/exampleUser/home/aws/listDProcessesNativeStacks.sh ubuntu@ip-172-31-69-105.ec2.internal:/home/ubuntu'
                        sh 'scp -i ${password} classproject/Google-Kubernetes-boilerplate/app/adservice/* ubuntu@35.183.109.118:~/'
                        sh 'scp -i ${password} dockerinstallscript.sh ubuntu@35.183.109.118:~/'
                    }    
                }
            }
        }
    }
}

    
