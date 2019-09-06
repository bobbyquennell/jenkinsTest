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
  post {
    success {
      slackSend(
        color: 'danger',
        message: "*${env.JOB_NAME}* build ${env.BUILD_NUMBER} failed\n\nMore details: ${env.BUILD_URL}",
        channel: '#jenkins'
      )
    }
  }
}
