pipeline {
  agent { dockerfile true }
  stages {
    stage('test') {
      steps {
        sh 'python3 test.py'
      }   
    }
  }
}
