pipeline {
  options {
    buildDiscarder(logRotator(numToKeepStr: '10'))
  }
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          sh '''
            SBI/build.sh
          '''
        }
      }
    }
    stage('Test') {
      steps {
        script {
          sh '''
            SBI/test.sh
          '''
        }
      }
    }
    stage('Build artifact') {
      steps {
        script {
          sh '''
            SBI/dockerize.sh
                      '''
        }
      }
    }
  }
}
