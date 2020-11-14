pipeline {
  agent {
    dockerfile true
  }
  stages {
    stage('Test') {
      steps {
        sh 'dotnet --version'
        sh 'cd tests'
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