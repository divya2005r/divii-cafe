pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                echo "Cloning done automatically by Jenkins"
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t divii-cafe .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop divii-container || true'
                sh 'docker rm divii-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8081:80 --name divii-container divii-cafe'
            }
        }
    }
}