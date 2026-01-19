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
        bat '''
        set KUBECONFIG=C:\\Users\\chara\\.kube\\config
        kubectl apply -f k8s/deployment.yaml --validate=false
        kubectl apply -f k8s/service.yaml --validate=false
        '''
    }
}

    }
}
