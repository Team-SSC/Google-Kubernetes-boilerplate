pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                git branch: 'serahbranch', credentialsId: 'd8398470-2dc7-4a8e-9001-df92ba6bd73b', url: 'https://github.com/Team-SSC/Google-Kubernetes-boilerplate.git'
                sh '''cd app/emailservice/
                       docker build . -t tolaoguntunde/emailservice
                       docker push tolaoguntunde/emailservice
                       '''
            }
        }
        }
                
    }
