pipeline {
    agent any;
    tools {
        nodejs 'nodejs-react'
    }
    stages {

        stage('Initialize') {
            steps {
                sh '''
                    npm install
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                    npm run test -- --watchAll=false
                '''
            }
        }

        stage('Build') {
            steps {
                sh '''
                    npm run build
                '''
            }
        }
    }
}
