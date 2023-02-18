pipeline {
    agent any
    environment {
        dockerhub=credentials('DockerHubCredentials')
    }

    stages {
        stage('Hello') {
            steps {
                sh ''' #cd $WORKSPACE/app/checkoutservice/
                       docker build -t shynedevs/checkoutservice:2 $WORKSPACE/app/checkoutservice/Dockerfile
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/checkoutservice:2
                       '''
               
            }
        }
        }
                
    }
