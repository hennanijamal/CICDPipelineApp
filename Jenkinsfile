pipeline {
  agent {
    node {
      label 'firstNodeLabel'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'php --version'
      }
    }
  }
  environment {
    testenv = 'testenvvalue'
  }
}