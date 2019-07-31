pipeline {
  agent any

  stages {
    stage('Lint HTML') {
      steps {
        sh 'tidy -q -e *.html'
      }
    }
    stage('Upload to AWS') {
      when {
            branch 'master'
          }
      steps {
        sh 'echo "Uploading: ./index.html to S3"'
        withAWS(region:'us-west-1',credentials:'34977218-6ce9-4ed5-8a95-f76365491d81') {
              s3Delete(bucket: 'cicdpp', path:'')
              s3Upload(file:'./index.html', bucket:'cicdpp', path:'', acl:'PublicRead')
            }
        sh '''
            echo "Finished Uploading ./index.html to S3"
            echo "Upload complete"
        '''
      }
    }
    
  }

}