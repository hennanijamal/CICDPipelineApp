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
    stage('Install Packages') {
      steps {
        sh 'npm install'
      }
    }
    stage('Install Lint HTML') {
      steps {
        sh 'node --version'
      }
    }
  }
  environment {
    testenv = 'testenvvalue'
  }
}