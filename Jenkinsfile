pipeline {
    agent any

    tools {
        nodejs 'NodeJS 16'  // Match the name configured in Jenkins Global Tool Config
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
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'npm test' // Only if you have test scripts
            }
        }

        stage('Build') {
            steps {
                echo 'Build step for Node.js app - can be dockerize or zip'
            }
        }

        stage('Check PM2') {
            steps {
                bat 'pm2 -v'
            }
        }

stage('Deploy') {
    steps {
        bat 'pm2 delete app || exit 0'
        bat 'pm2 start app.js --name app'
    }
}
    }
}
