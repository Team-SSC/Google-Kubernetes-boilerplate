pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh '''cd app/shippingservice/
                       docker build . -t tsp/shippingservice
                       docker push tsp/shippingservice
                       '''
            }
        }
        }
                
    }
