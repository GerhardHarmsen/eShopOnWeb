pipeline {
  agent any
  stages {
    stage('Build ') {
      steps {
        sh '''sh \'docker-compose build\'
sh \'docker-compose up\''''
        echo 'Check complete'
      }
    }

  }
}