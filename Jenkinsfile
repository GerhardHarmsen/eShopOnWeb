epipeline {
  agent {
    dockerfile {
      dir src/Web 
    }
  }
  stages {
    stage('Test') {
      steps {
        sh 'node --version'
        sh 'svn --version'
      }
    }

  }
}
