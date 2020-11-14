pipeline {
  agent {
    docker {
      image 'src/Web/Dockerfile'
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