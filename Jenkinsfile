pipeline {
    agent any
    environment {
        dockerhub=credentials('DockerHubCredentials')
    }
    stages {
        stage('Build all Docker Images and Push to DockerHub') {
            steps {
                sh ''' #cd $WORKSPACE/app/checkoutservice/
                       docker build -t shynedevs/adservice:2 $WORKSPACE/app/adservice/
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/adservice:2
                       docker rmi shynedevs/adservice:2

                       docker build -t shynedevs/checkoutservice:4 $WORKSPACE/app/checkoutservice/
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/checkoutservice:4

                       docker build -t shynedevs/currencyservice:2 $WORKSPACE/app/currencyservice/
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/currencyservice:2

                       docker build -t shynedevs/emailservice $WORKSPACE/app/emailservice/
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/emailservice

                       docker build -t shynedevs/frontend $WORKSPACE/app/frontend/
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/frontend

                       docker build -t shynedevs/loadgenerator $WORKSPACE/app/loadgenerator/
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/loadgenerator

                       docker build -t shynedevs/paymentservice $WORKSPACE/app/paymentservice/
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/paymentservice

                       docker build -t shynedevs/productcatalogservice $WORKSPACE/app/productcatalogservice/
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/productcatalogservice

                       docker build -t shynedevs/recommendationservice $WORKSPACE/app/recommendationservice/
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/recommendationservice

                       docker build -t shynedevs/shippingservice:2 $WORKSPACE/app/shippingservice/
                       echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
                       docker push shynedevs/shippingservice:2

                       '''              
            }
        }
    }             
}
