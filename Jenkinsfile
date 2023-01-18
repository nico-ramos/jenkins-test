def access_token = 'initial'
pipeline {
    agent { docker { image 'node:16.17.1-alpine' } }
    stages {
        stage('build') {
            steps {
                sh 'node --version'
            }
        }
        stage('Get Access Key') {
            steps {
              script {
                access_token = sh(script: 'node steps/auth_step.js', returnStdout: true)
              }
            }
        }
        stage('Test auth') {
            steps {
                script {
                  sh """node steps/test1.js ${access_token}"""
                }
            }
        }
    }
}