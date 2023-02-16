pipeline {
    agent any
    environment {
        dockerhub=credentials('DockerHubCredentials')
    }

    stages {
        stage('Hello') {
            steps {
                sh '''cd app/shippingservice/
                       docker build . -t shynedevs/shippingservice  
                       docker login -u "shynedevs" -p "Gd7_Ve%hfB-y5gX" docker.io/shynedevs
                       docker push shynedevs/shippingservice
                       '''
               
            }
        }
        }
                
    }
