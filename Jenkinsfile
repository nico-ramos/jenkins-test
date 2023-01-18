pipeline {
    agent { docker { image 'node:16.17.1-alpine' } }
    stages {
        stage('build') {
            steps {
                sh 'node --version'
            }
        }
        stage('uno') {
            steps {
                sh 'node pipe1.js'
            }
        }
        stage('dos') {
            steps {
                sh 'node pipe2.js'
            }
        }
    }
}