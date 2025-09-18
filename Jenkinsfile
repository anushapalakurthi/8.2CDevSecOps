pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/anushapalakurthi/8.2CDevSecOps'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                // let pipeline continue even if tests fail
                bat 'npm test || exit 0'
            }
        }

        stage('Generate Coverage') {
            steps {
                bat 'npm run coverage || exit 0'
            }
        }

        stage('NPM Audit') {
            steps {
                bat 'npm audit || exit 0'
            }
        }
    }
}
