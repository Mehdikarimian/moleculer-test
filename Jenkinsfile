pipeline {
    agent { docker { image 'node:8-alpine' } }
    stages {
        stage('build') {
            steps {
                sh 'npm --version'
                sh 'npm install'
            }
        }
        stage('test') {
          steps {
            sh 'npm run test'
          }
        }
        stage('run') {
          steps {
            sh 'npm start'
          }
    }
}
