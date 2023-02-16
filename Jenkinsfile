pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh '''cd app/shippingservice/
                       docker build . -t shynedevs/shippingservice                       
                       '''
                withCredentials([usernamePassword(credentialsId: 'DockerHubCredentials', passwordVariable: 'password', usernameVariable: 'username')]) {
                    sh 'docker login -u ${username} -p ${password} docker.io/shynedevs'
                    sh 'docker push shynedevs/shippingservice'
                }
            }
        }
        }
                
    }
