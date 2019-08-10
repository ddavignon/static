pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      steps {
        tidy -q -e *.html
      }
    }
    stage('Upload to AWS') {
      steps {
        withAWS(credentials:'aws-static') {
          s3Upload(file:'index.html', bucket:'ddavignon-udacity-proj4', path:'index.html')
        }
      }
    }
  }
}