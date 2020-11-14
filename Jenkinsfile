pipeline {
  agent {
    dockerfile {
      filename '/src/Web/Dockerfile'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build'
      }
    }

  }
}