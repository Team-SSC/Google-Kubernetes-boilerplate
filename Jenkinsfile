pipeline{
    agent any
    stages{
        stage("Create Images"){
            steps{
                echo "===x=====executing A========"
                sh "pwd"
                sh "docker build -f ~/app/adservice/Dockerfile"
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