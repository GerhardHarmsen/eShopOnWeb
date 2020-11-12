pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '*/src/PublicApi/ docker build'
      }
    }

  }
}