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
      steps {
        sh '''cd tests
cd FunctionalTests

'''
        dotnetRestore()
        dotnetBuild()
        dotnetTest()
      }
    }

  }
}