pipeline {
    agent any

    environment {
        IMAGE_NAME = 'venky005/devops-app'
    }

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME:latest .'
            }
        }

        stage('Login to DockerHub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker-creds',
                usernameVariable: 'USER', passwordVariable: 'PASS')]) {
                    sh 'echo $PASS | docker login -u $USER --password-stdin'
                }
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push $IMAGE_NAME:latest'
            }
        }

        stage('List Images') {
            steps {
                sh 'docker images'
            }
        }
    }
}