pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/nileshwanare1/GitHub_Jenkins_Docker_AWS-EC2.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f my-container || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d -p 80:80 --name my-container my-app'
            }
        }
    }
}