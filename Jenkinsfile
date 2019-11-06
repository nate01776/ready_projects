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
        sh '''apt-get install
apt-get install nodejs
apt-get update
'''
        sh 'npm install -g testengine-cli'
        sh 'ls'
      }
    }

  }
}