pipeline {
    agent any

    environment {
        IMAGE_NAME = 'venkat8977/devops-app'
    }

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/venkat8977/devops-project-1.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME:latest .'
            }
        }

        stage('List Images') {
            steps {
                sh 'docker images'
            }
        }
    }
}