pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
    parallelsAlwaysFailFast()
  }
  environment {
    DOCKERHUB_CREDENTIALS = credentials('dockerhub')
    DOCKER_REGISTRY = "sameh/python/"
    version = (sh (script: 'xmlstarlet sel -t -m "/Version/images-version" -v . -n VERSION.xml',returnStdout: true)).trim()
    backendImage = "${DOCKER_REGISTRY}" + "backend-image"
  }
  stages {
    stage('dependencies') {
      steps {
        script {
                // Update the package list
                sh 'sudo apt-get update'

                // Install xmlstarlet
                sh 'sudo apt-get install -y xmlstarlet'
                }
      }      
    }    
    stage('Build') {
      steps {
        sh 'echo "testttt". '
        sh """ echo version is -------- ${version} """
        sh """ echo version is -------- ${backendImage} """
      }
    }
   
}
}