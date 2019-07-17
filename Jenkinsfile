pipeline {
  agent {
    docker {
      image 'node:10-alpine'
      args '-p 20001-20100:3000'
    }
  }
  environment {
    CI = 'true'
    HOME = '.'
    npm_config_cache = 'npm-cache'
  }
  stages {
    stage('build') {
      steps {
        echo 'php --version'
      }
    }
    stage('Install Packages') {
      steps {
        sh 'npm install htmllint-cli'
      }
    }
    stage('Install Lint HTML') {
      steps {
        sh 'node --version'
      }
    }
    stage('Production') {
          when {
            branch 'master'
          }
          steps {
            withAWS(region:'us-west-1',credentials:'34977218-6ce9-4ed5-8a95-f76365491d81') {
              s3Delete(bucket: 'cicdpp', path:'/')
              s3Upload(file:'/', bucket:'cicdpp', path:'/')
            }
          }
    }
  }
  
}