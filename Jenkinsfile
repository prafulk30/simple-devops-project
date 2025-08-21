pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/prafulk30/simple-devops-project.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t simple-devops-app:${BUILD_NUMBER} .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 simple-devops-app:${BUILD_NUMBER}'
            }
        }
    }
}
