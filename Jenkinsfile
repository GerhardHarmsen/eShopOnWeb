pipeline {
  agent {
    dockerfile {
      args '-it --entrypoint='
    }

  }
  stages {
    stage('Test') {
      steps {
        dotnetTest configuration: 'Release', project: 'tests/FunctionalTests', sdk: 'DotNet', unstableIfWarnings: true, workDirectory: 'tests/FunctionalTests'
      }
    }

    stage('Unit tests') {
      parallel {
        stage('Functional Tests') {
          steps {
            sh '''cd tests
cd FunctionalTests
dotnet --version'''
            sh '''dotnet restore
dotnet build
dotnet test'''
          }
        }

        stage('IntegrationTest') {
          steps {
            sh '''cd tests 
cd IntegrationTests'''
            sh '''dotnet restore
dotnet build
dotnet test'''
          }
        }

        stage('UnitTests') {
          steps {
            sh '''cd tests
cd UnitTests'''
            sh '''dotnet restore
dotnet build
dotnet test'''
          }
        }

      }
    }

    stage('error') {
      steps {
        echo 'Pipeline complete'
      }
    }

  }
}
