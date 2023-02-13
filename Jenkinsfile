pipeline{
    agent any
    stages{
        stage("Create Images"){
            agent { dockerfile true }      
            steps{
                echo "===x=====executing A========"
                sh "pwd"
                sh "cd app/adservice/"
                sh "docker build ."
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
    
