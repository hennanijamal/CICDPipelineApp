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
  }
  environment {
    testenv = 'testenvvalue'
  }
}