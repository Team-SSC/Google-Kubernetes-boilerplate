pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh '''cd app/shippingservice/
                       docker build . -t shynedevs/shippingservice  
                       sh 'docker login -u "shynedevs" -p "Gd7_Ve%hfB-y5gX" docker.io/shynedevs'
                       sh 'docker push shynedevs/shippingservice'
                       '''
               
            }
        }
        }
                
    }
