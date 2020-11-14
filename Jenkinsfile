pipeline {
  agent {
    dockerfile { args '-it --entrypoint='}
  }
  stages {
    stage('Test') {
      steps {
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
