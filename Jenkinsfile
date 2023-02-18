pipeline {
    agent any
    environment {
        dockerhub=credentials('DockerHubCredentials')
    }

    stages {
        stage('Hello') {
            steps {
                sh ''' #cd $WORKSPACE/app/checkoutservice/
                       docker build -t shynedevs/adservice $WORKSPACE/app/adservice/
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/adservice

                       docker build -t shynedevs/currencyservice $WORKSPACE/app/currencyservice/
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/currencyservice

                       docker build -t shynedevs/checkoutservice:3 $WORKSPACE/app/checkoutservice/
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/checkoutservice:3
                       '''
               
            }
        }
        }
                
    }
