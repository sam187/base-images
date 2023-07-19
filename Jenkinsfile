pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
    parallelsAlwaysFailFast()
  }
  environment {
    DOCKERHUB_CREDENTIALS = credentials('dockerhub')
    version = (sh (script: 'xmlstarlet sel -t -m "/Version/images-version" -v . -n VERSION.xml',returnStdout: true)).trim()
  }
  stages {
    stage('Build') {
      steps {
        sh 'echo "testttt". '
        sh """ echo version is -------- ${version} """
      }
    }
   
}
}