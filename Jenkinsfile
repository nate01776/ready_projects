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
      parallel {
        stage('regression') {
          steps {
            sh 'testengine --version'
          }
        }

        stage('smoke') {
          steps {
            sh 'testengine --version'
          }
        }

        stage('functional') {
          steps {
            sh 'testengine --version'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy!'
      }
    }

  }
}