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
        sh 'apt-get install curl'
        sh 'curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -'
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