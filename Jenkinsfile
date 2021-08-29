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
        stage("Upload"){
            steps{
                withAWS(region:'us-east-1',credentials:'S3-Artifacts') {
                    def identity = awsIdentity()

                    s3Upload(bucket:"22088-amanpatwa", workingDir:'temp1', includePathPattern:'build/*');
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

