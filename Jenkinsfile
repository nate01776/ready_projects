pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'alpine:latest'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'apk add --update nodejs npm'
        sh '''node --version
npm --version
'''
        sh 'npm install -g testengine-cli'
        sh 'testengine --version'
        sh 'ls'
      }
    }

  }
}