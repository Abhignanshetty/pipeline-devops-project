pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t abhignashetty/ci-mini-app:latest .'
            }
        }

       stage('Push to Docker Hub') {
    steps {
        withCredentials([usernamePassword(credentialsId: 'dockerhub',
        usernameVariable: 'DOCKER_USER',
        passwordVariable: 'DOCKER_PASS')]) {

            sh '''
            docker login -u $DOCKER_USER -p $DOCKER_PASS
            docker push abhignashetty/ci-mini-app:latest
            '''
        }
    }
}

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}