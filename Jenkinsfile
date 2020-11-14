pipeline {
  agent {
    dockerfile true
  }
  stages {
    stage('Test') {
      steps {
        sh 'docker run'
      }
    }

    stage('Unit tests') {
      steps {
        sh '''cd FunctionalTests
dotnet restore 
dotnet build
dotnet test
'''
      }
    }

  }
}