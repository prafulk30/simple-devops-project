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
        bat '''
        REM __define-ocg__ stop old container if running (suppress errors)
        docker stop simple-devops-container 2>nul || echo "No container to stop"
        docker rm simple-devops-container 2>nul || echo "No container to remove"

        REM Run new container with fixed name
        docker run -d -p 5002:5000 --name simple-devops-container simple-devops-app
        '''
        }
        }
    }
}
