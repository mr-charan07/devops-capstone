pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t flask-phase2 .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f k8s/deployment.yaml --validate=false'
                bat 'kubectl apply -f k8s/service.yaml --validate=false'
            }
        }
    }
}
