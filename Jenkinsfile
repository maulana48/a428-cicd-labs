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
            stage('Test') { 
                steps {
                    sh './jenkins/scripts/test.sh' 
                }
            }
            stage('Deploy') {
                steps {
                    sh './jenkins/scripts/deliver.sh'
                    input message: 'Sudah selesai menggunakan React App? (Klik "Proceed" untuk mengakhiri)'
                    sh './jenkins/scripts/kill.sh'
                }
            }
        }
    }