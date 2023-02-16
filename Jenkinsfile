pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh '''cd app/shippingservice/
                       docker build . -t shynedevs/shippingservice
                       docker push shynedevs/shippingservice
                       '''
            }
        }
        }
                
    }
