pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'echo build'
        sh '''docker-compose.yml build
'''
      }
    }

  }
  environment {
    eShopTest = '8080'
  }
}