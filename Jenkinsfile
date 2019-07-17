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
        echo 'test build'
      }
    }
    stage('Install Lint HTML') {
      steps {
        sh 'su npm install -g htmllint-cli'
      }
    }
    stage('Lint HTML') {
      steps {
        sh 'htmllint ./index.html'
      }
    }
    stage('Production') {
          when {
            branch 'master'
          }
          steps {
            withAWS(region:'us-west-1',credentials:'34977218-6ce9-4ed5-8a95-f76365491d81') {
              s3Delete(bucket: 'cicdpp', path:'')
              s3Upload(file:'./index.html', bucket:'cicdpp', path:'', acl:'PublicRead')
            }
          }

    }
  }
  environment {
    CI = 'true'
    HOME = '.'
    npm_config_cache = 'npm-cache'
  }
}