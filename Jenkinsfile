node {
    docker.image('node:16-buster-slim').withRun('-p 3000:3000').inside {
        
        // Stage: Build
        stage('Build') {  
            // Install dependencies
            sh 'npm install'
        }

        // Stage: Test
        stage('Test') {
            // Run test script
            sh './jenkins/scripts/test.sh'
        }
    }
}
