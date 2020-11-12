pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'echo build'
        sh 'make'
      }
    }

  }
  environment {
    eShopTest = '8080'
  }
}