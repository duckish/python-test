pipeline {
  agent { dockerfile true }
  stages {
    stage('test') {
      steps {
        sh 'python3 test.py'
      }   
    }

    stage('Build image') {
      steps {
        sh "docker build -t your-app:${GIT_SHA} ."
      }
    }
        
  }
}
