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
        sh 'node --version'
        sh 'npm --version'
        sh 'npm install -g testengine-cli'
      }
    }

    stage('Stage') {
      steps {
        sh 'ls'
      }
    }

    stage('Test') {
      steps {
        sh 'testengine -c ./testengine.conf run project output=./results format=junit ./random_pass_fail.xml'
        sh 'ls ./results'
        junit './results/*.xml'
      }
    }

  }
}