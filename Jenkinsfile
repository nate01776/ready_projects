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
        sh 'npm install -g testengine-cli'
        sh 'testengine --version'
        sh 'ls'
      }
    }

  }
}