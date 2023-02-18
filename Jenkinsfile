pipeline {
    agent any
    environment {
        dockerhub=credentials('DockerHubCredentials')
    }

    stages {
        stage('Hello') {
            steps {
                sh ''' cd $WORKSPACE/app/checkoutservice/
                       docker build . -t shynedevs/checkoutservice:1
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/checkoutservice:1
                       '''
               
            }
        }
        }
                
    }
