
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Downloading code from GitHub...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building web application...'
                sh 'npm install'
                sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment stage completed'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed! Check console logs.'
        }
    }
}
