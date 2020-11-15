pipeline {
  agent {
    dockerfile {
      args '-it --entrypoint='
    }

  }
  stages {
    stage('Test') {
      steps {
        sh 'cd tests'
      }
    }

    stage('Unit tests') {
      parallel {
        stage('Functional Tests') {
          steps {
            sh '''cd tests
cd FunctionalTests

'''
            dotnetRestore()
            dotnetBuild()
            dotnetTest()
          }
        }

        stage('IntegrationTest') {
          steps {
            sh '''cd tests 
cd IntegrationTests'''
            dotnetToolRestore()
            dotnetBuild()
            dotnetTest()
          }
        }

        stage('UnitTests') {
          steps {
            sh '''cd test
cd UnitTests'''
            dotnetRestore()
            dotnetBuild()
            dotnetTest()
          }
        }

      }
    }

    stage('') {
      steps {
        echo 'Pipeline complete'
      }
    }

  }
}