pipeline {
  agent {
    docker {
      image 'node:6.3'
    }

  }
  stages {
    stage('build') {
      steps {
        echo 'hi there'
      }
    }
  }
  environment {
    testenv = 'testenvvalue'
  }
}