node {
    docker.image('node:16-buster-slim').withRun('-p 3000:3000') {
        
        // Stage: Build
        stage('Build') {  
            // Install dependencies
            sh '/bin/npm install'
        }

        // Stage: Test
        stage('Test') {
            // Run test script
            sh './jenkins/scripts/test.sh'
        }
    }
}
