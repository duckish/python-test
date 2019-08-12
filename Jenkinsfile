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
        
        script {
          def scmVars = checkout([
          $class: 'GitSCM'
          ])

          echo "scmVars.GIT_COMMIT"
          echo "${scmVars.GIT_COMMIT}"

          env.GIT_COMMIT = scmVars.GIT_COMMIT
          echo "env.GIT_COMMIT"
          echo "${env.GIT_COMMIT}"
          sh "docker build -t your-app:${env.GIT_COMMIT} ."
        }

      }
    }
        
  }
}
