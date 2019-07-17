pipeline {
  agent any
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
  }
  environment {
    testenv = 'testenvvalue'
  }
}