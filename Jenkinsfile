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
        sh 'apt-get update'
        sh '''((echo "Y")) | apt install nodejs
((echo "Y")) | apt install npm
node --version
npm --version
'''
        sh 'npm install -g testengine-cli'
        sh 'testengine --version'
      }
    }

  }
}