
pipeline {
    agent any

    environment {
        DEPLOY_DIR = 'C:\\inetpub\\wwwroot'
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Downloading code from GitHub...'
                git branch: 'main',
                url: 'https://github.com/rutiuja/CI-CD-Webapp.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building web application...'
                bat 'dir'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing HTML files...'
                bat 'tidy -q -e index.html'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying website...'
                bat 'if not exist "%DEPLOY_DIR%" mkdir "%DEPLOY_DIR%"'
                bat 'xcopy /E /I /Y * "%DEPLOY_DIR%\\"'
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
