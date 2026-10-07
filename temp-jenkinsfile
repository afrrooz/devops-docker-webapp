pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/afrrooz/devops-docker-webapp.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t afrrooz/devops-webapp:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d --name devops-webapp -p 3000:3000 afrrooz/devops-webapp:latest'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }

        always {
            echo 'Pipeline finished.'
        }
    }
}
