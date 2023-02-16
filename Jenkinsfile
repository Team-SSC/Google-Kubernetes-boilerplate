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
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/shippingservice
                       '''
               
            }
        }
        }
                
    }
