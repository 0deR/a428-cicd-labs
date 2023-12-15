node {
    // This block specifies that the entire pipeline will run on a single Jenkins agent (node).
    checkout scm
    // Define Docker agent
    docker.withServer('tcp://docker:2376'){
    docker.image('node:16-buster-slim').inside {
    sh 'npm install'
        // // Environment variables
        // env.CI = 'true'

        // // Build stage
        // stage('Build') {
        //     steps {
        //         sh 'npm install'
        //     }
        // }

        // // Test stage
        // stage('Test') {
        //     steps {
        //         sh './jenkins/scripts/test.sh'
        //     }
        // }

        // // Deliver stage
        // stage('Deliver') {
        //     steps {
        //         sh './jenkins/scripts/deliver.sh'
                
        //         // Input step for user interaction
        //         input message: 'Finished using the website? (Click "Proceed" to continue)'
                
        //         // Additional steps after user input
        //         sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
}
