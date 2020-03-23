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
        sh 'mkdir ./results'
      }
    }

    stage('Run Tests') {
      parallel {
        stage('Suite A') {
          steps {
            sh 'testengine -c ./testengine.conf run project testsuite="TestSuite A" output=results/A format=junit ./random_pass_fail.xml'
            junit 'results/A/*.xml'
          }
        }

        stage('Suite B') {
          steps {
            sh 'testengine -c ./testengine.conf run project testsuite="TestSuite B" output=results/B format=junit ./random_pass_fail.xml'
            junit 'results/B/*.xml'
          }
        }

        stage('Suite C') {
          steps {
            sh 'testengine -c ./testengine.conf run project testsuite="TestSuite C" output=results/C format=junit ./random_pass_fail.xml'
            junit 'results/C/*.xml'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deployed'
      }
    }

  }
}