pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 umarani800/registration:v1'
                bat 'docker push umarani800/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f C:/Users/sadhv/OneDrive/Desktop/DevOps1271/Week-2/deployment.yaml'
                bat 'kubectl apply -f C:/Users/sadhv/OneDrive/Desktop/DevOps1271/Week-2/service.yaml'
            }
        }
        stage('Automated UI Test') {
            steps {
                bat 'python C:/Users/sadhv/OneDrive/Desktop/DevOps1271/Week-2/test_registration.py'
            }
        }
    }
}
