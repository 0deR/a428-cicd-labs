node {
    docker.image('node:16-buster-slim').withRun('-p 3000:3000') {
        
        // Stage: Build
        stage('Build') {
            // Set npm timeout
            sh 'npm config set timeout 6000000'
            
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
