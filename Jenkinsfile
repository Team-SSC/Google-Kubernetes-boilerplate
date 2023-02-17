pipeline {
    agent any
    environment {
        dockerhub=credentials('DockerHubCredentials')
    }

    stages {
        stage('Hello') {
            steps {
                sh ''' cd app/checkoutservice/
                       docker build . -t shynedevs/checkoutservice
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/checkoutservice
                       
                       cd app/adservice/
                       docker build . -t shynedevs/adservice
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/adservice
                       '''
               
            }
        }
        }
                
    }
