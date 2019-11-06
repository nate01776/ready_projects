pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'node:6'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install -g --no-optional testengine-cli'
        sh 'testengine --version'
        sh 'ls'
      }
    }

  }
}