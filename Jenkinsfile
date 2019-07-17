pipeline {
  agent {
    docker {
      image 'node:10-alpine'
      args '-p 20001-20100:3000'
    }
  }
  stages {
    stage('build') {
      steps {
        echo 'php --version'
      }
    }
    stage('Lint HTML') {
      steps {
        echo 'Lint HTML'
      }
    }
    stage('Install Lint HTML') {
      steps {
        echo 'node --version'
      }
    }
  }
  environment {
    testenv = 'testenvvalue'
  }
}