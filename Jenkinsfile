pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps { git branch: 'main', url: 'https://github.com/sanju123-s/Jen' }
        }

        stage('Docker Build') {
            steps { sh 'docker build -t flask-app:1.0 .' }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh '''
                kubectl apply -f deployment.yaml
                kubectl apply -f service.yaml
                '''
            }
        }
    }
}
