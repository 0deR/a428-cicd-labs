node {
    // This block specifies that the entire pipeline will run on a single Jenkins agent (node).
    checkout scm
    // Define Docker agent
    docker.withServer('tcp://docker:2376'){
    docker.image('node:16-buster-slim').inside {
                stage('Install Dependecies') {
                          sh 'npm install'
                }
            stage('Test Script') {
                sh './jenkins/scripts/test.sh'
            }
                             
            }
        }
    }
