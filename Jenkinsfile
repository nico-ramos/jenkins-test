def access_token = 'initial'
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
                access_token = sh(script: 'node pipe1.js', returnStdout: true)
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