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
        
        stage('Upload') {
            steps{
                sh '''
                echo "========executing build Stage========"  
                '''
            }
            options {
                withAWS(region: 'us-east-1', role: 'PE-Training-2021'){
                    s3Upload(bucket:"22088-amanpatwa/temp1",includePathPattern:"build/*")
                }
            }
        }


        
    }
}

// pipeline{
//     agent{
//         label "jenkins-agent3"
//     }
//     tools {
//         nodejs 'nodejs'
//     }
//     stages{
//         stage("Initialize"){
//             steps{
//                 sh '''
//                     echo "========executing initialize Stage========"
//                     npm install
//                 '''
//             }
//         }
//         stage("Test"){
//             steps{
//                 sh '''
//                     echo "========executing testing Stage========"
//                     npm run test --watchAll=false
//                 '''
//             }
//         }
//         stage("Build"){
//             steps{
//                 sh '''
//                     echo "========executing build Stage========"
//                     npm run build
//                 '''
//             }
//         }
//     }
// }

