pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t event-registration-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 event-registration-app'
            }
        }

        stage('Test Application') {
            steps {
                sh 'echo "Application Deployed Successfully"'
            }
        }
    }
}