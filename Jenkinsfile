    pipeline {
        agent {
            docker {
                image 'node:16-buster-slim' 
                args '-p 3000:3000' 
            }
        }
        stages {
            stage('Build') { 
                steps {
                    sh 'npm config set fetch-retry-mintimeout 20000'
                    sh 'npm config set fetch-retry-maxtimeout 120000' 
                    sh 'npm install' 
                }
            }
        }
    }