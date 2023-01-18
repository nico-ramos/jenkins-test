pipeline {
    agent { docker { image 'node:16.17.1-alpine' } }
    environment {
      ACCESS_TOKEN = 'initial'
    }
    stages {
        stage('build') {
            steps {
                sh 'node --version'
            }
        }
        stage('Get Access Key') {
            steps {
              script {
                ACCESS_TOKEN = sh(script: 'node steps/auth_step.js', returnStdout: true)
              }
            }
        }
        stage('dos') {
            steps {
                script {
                  sh 'node steps/test1.js'
                }
            }
        }
    }
}