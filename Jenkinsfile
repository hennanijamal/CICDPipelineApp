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
    stage('Install Lint HTML') {
      steps {
        echo "node -v"
      }
    }
  }
  environment {
    testenv = 'testenvvalue'
  }
}