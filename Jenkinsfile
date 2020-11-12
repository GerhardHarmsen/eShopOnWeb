pipeline {
  agent {
    docker {
      image 'docker-compose'
      args '''docker-compose build 
docker-compose up'''
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