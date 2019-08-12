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
                echo 'Starting to build docker image'

                script {
                    def customImage = docker.build("my-image:${env.BUILD_ID}")
                    customImage.push()
                }
            }
        }
  }
}
