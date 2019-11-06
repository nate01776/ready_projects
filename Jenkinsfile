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

    stage('regression') {
      steps {
        sh 'testengine -c ./testengine.conf run project output=./results format=junit ./random_pass_fail.xml'
      }
    }

    stage('Archive Results') {
      steps {
        sh 'ls ./results'
        junit(testResults: './results/*.xml', allowEmptyResults: true)
      }
    }

    stage('Deploy') {
      steps {
        echo 'Hello, world!'
      }
    }

  }
}