pipeline {
  agent {
    dockerfile {
      filename 'firstdosckerfile'
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