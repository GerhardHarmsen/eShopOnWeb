pipeline {
  agent {
    dockerfile true
  }
  stages {
    stage('Test') {
      steps {
        sh 'node --version'
        sh 'svn --version'
      }
    }

    stage('Unit tests') {
      steps {
        sh '''cd tests
cd FunctionalTests
dotnet restore 
dotnet build
dotnet test
'''
      }
    }

  }
}