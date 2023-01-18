def access_token = ''
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
              script {
                access_token = sh 'node pipe1.js'
              }
            }
        }
        stage('dos') {
            steps {
                script {
                  echo access_token
                  sh 'node pipe2.js'
                }
            }
        }
    }
}