pipeline{
    agent{
        label "jenkins-agent3"
    }
    tools {
        nodejs 'nodejs'
    }
    stages{
        stage("Initialize"){
            steps{
                sh '''
                    echo "========executing initialize Stage========"
                    npm install
                '''
            }
        }
        stage("Test"){
            steps{
                sh '''
                    echo "========executing testing Stage========"
                    npm run test --watchAll=false
                '''
            }
        }
        stage("Build"){
            steps{
                sh '''
                    echo "========executing build Stage========"
                    npm run build
                '''
            }
        }
    }
}
