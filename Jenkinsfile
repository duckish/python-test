pipeline {
  agent { dockerfile true }
  stages {
    stage('test') {
      steps {
        sh 'python3 test.py'
      }   
    }
    stage('build') {
      steps {
        def customImage = docker.build("my-image:${env.BUILD_ID}")
      }
    }
  }
}
