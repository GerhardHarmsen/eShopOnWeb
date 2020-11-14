pipeline {
  agent {
    dockerfile { args '-it --entrypoint=/bin/bash'}
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
        sh '''cd FunctionalTests
dotnet restore 
dotnet build
dotnet test
'''
      }
    }

  }
}
