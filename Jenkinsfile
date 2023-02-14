pipeline{
    agent any
    stages{
        stage("Copy files to Docker Server"){
            //agent { dockerfile true }      
            steps{
                echo "===x=====executing A========"
                sh "pwd"
                sh "scp classproject/Google-Kubernetes-boilerplate/app/adservice/* ubuntu@35.183.109.118:~/"
                sh "scp dockerinstallscript.sh ubuntu@35.183.109.118:~/"
                //sh "cd app/adservice/"
                //sh "docker build ."
                //sh "docker build . -t testapp"
            }
        }

        stage("connect to Docker server"){

            environment { 
                SSH_CRED = credentials('sshCredentials')
            }

            steps {
                script {
                    sh """
                    #!/bin/bash
                    ssh -i $SSH_CRED -t -o StrictHostKeyChecking=no ubuntu@35.183.109.118 << EOF
                    sudo chmod 777 dockerinstallscript.sh
                    sh dockerinstallscript.sh
                    docker build . -t apserviceimage 
                    #curl ifconfig.co/ip
                    #df -h
                    exit
                    << EOF
                    """
                }
                
            }
        }
        stage("Push Image to Dockerhub"){
            steps{
                echo "========executing A========"
            }
        }
        stage(""){
            steps{
                echo "========executing A========"
            }
        }
    }
}
    
