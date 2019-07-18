pipeline {
  agent {
    docker {
      image 'node:10-alpine'
      args '-p 20001-20100:3000'
    }

  }
  stages {
    stage('Install Packages') {
      steps {
        sh 'npm install'
      }
    }
    stage('Lint HTML') {
      steps {
        sh 'npm run test'
      }
    }
    stage('deployment') {
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
    stage('Test for website existence') {
      steps {
        sh 'npm run existtest'
      }
    }
  }
  environment {
    CI = 'true'
    HOME = '.'
    npm_config_cache = 'npm-cache'
  }
}