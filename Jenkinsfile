pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/vaibhavdatkhil/event-registration-devops.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t event-registration-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f event-app || true'
                sh 'docker run -d -p 5000:5000 --name event-app event-registration-app'
            }
        }

        stage('Test Application') {
            steps {
                sh 'echo "Application Deployed Successfully"'
            }
        }
    }
}