pipeline {
    agent any

    tools {
        nodejswg'NodeJS 16'  // Match the name configured in Jenkins Global Tool Config
    }

    environment {
        APP_NAME = 'my-node-app'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/saikiran-devOpss/node-js-dev.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test' // Only if you have test scripts
            }
        }

        stage('Build') {
            steps {
                echo 'Build step for Node.js app - can be dockerize or zip'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy step - SCP to server or restart pm2 etc.'
            }
        }
    }
}
