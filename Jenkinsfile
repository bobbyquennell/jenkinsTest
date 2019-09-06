pipeline {
  agent { docker { image 'node:6.3' } }
  stages {
    stage('build') {
      steps {
        sh 'npm --version'
        sh 'echo "hello world"'
        sh '''
          echo "Multiline Shell steps works too"
          ls -lah
        '''
      }
    }
  }
}
