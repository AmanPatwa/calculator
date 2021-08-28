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
                echo "========executing initialize Stage========"
                npm install
            }
        }
        stage("Test"){
            steps{
                echo "========executing testing Stage========"
                npm run test -- --watchAll=false
            }
        }
        stage("Build"){
            steps{
                echo "========executing build Stage========"
                npm run build
            }
        }
    }
}
