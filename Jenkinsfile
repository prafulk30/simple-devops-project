pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/prafulk30/simple-devops-project.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t simple-devops-app .'
            }
        }
        stage('Run Container') {
            steps {
                bat 'docker run -d -p 5001:5000 simple-devops-app'
            }
        }
    }
}
