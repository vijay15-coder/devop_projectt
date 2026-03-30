pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/MohammedxFarman/devops-mini-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t feedback-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f feedback-container || true'
                sh 'docker run -d -p 5000:5000 --name feedback-container feedback-app'
            }
        }
    }
}
