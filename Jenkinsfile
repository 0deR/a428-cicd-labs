node {
    // This block specifies that the entire pipeline will run on a single Jenkins agent (node).
    
    // Define Docker agent
    docker.image('node:lts-buster-slim').withRun('-p 3000:3000') {

        // Environment variables
        env.CI = 'true'

        // Build stage
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        // Test stage
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }

        // Deliver stage
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                
                // Input step for user interaction
                input message: 'Finished using the website? (Click "Proceed" to continue)'
                
                // Additional steps after user input
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
