pipeline {
  agent {
    dockerfile {
      filename 'docker-compose'
    }

  }
  stages {
    stage('build') {
      steps {
        sh '''docker-compose build
docker-compose up'''
      }
    }

  }
  environment {
    eShopTest = '8080'
  }
}