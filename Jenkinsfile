pipeline {
  agent {
    docker {
      image 'node:8-alpine'
    }

  }
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
    stage('build docker') {
      steps {
        withEnv(["PATH=$PATH:~/.local/bin"]) {
          sh 'docker-compose --version'
          sh 'docker-compose build'
        }
      }
    }
    stage('run docker') {
      steps {
        withEnv(["PATH=$PATH:~/.local/bin"]) {
          sh 'docker-compose up -d'
        }
      }
    }
  }
  environment {
    PATH = '~/.local/bin'
  }
}
