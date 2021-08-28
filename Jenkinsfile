pipeline {
    agent {
        node "jenkins-agent1"
    }
    tools {
        nodejs 'nodejs-react'
    }
    stages {

        stage('Initialize') {
            steps {
                sh '''
                    echo 'Initializing.....'
                    npm install
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                    echo 'Running test.....'
                    npm run test -- --watchAll=false
                '''
            }
        }

        stage('Build') {
            steps {
                sh '''
                    echo 'Building.....'
                    npm run build
                '''
            }
        }
    }
}

