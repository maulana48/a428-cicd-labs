    pipeline {
        agent {
            docker {
                image 'node:16-buster-slim' 
                args '-p 3333:3333' 
            }
        }
        stages {
            stage('Build') { 
                steps {
                    sh 'npm install' 
                }
            }
        }
    }