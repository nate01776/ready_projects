pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'ubuntu:latest'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh '''apt install nodejs
node --version
npm --version
'''
        sh 'npm install -g testengine-cli'
        sh 'ls'
      }
    }

  }
}