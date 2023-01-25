pipeline {
  agent any
  stages {
    stage('Parallel execution') {
      parallel {
        stage('hello') {
          steps {
            echo 'Hello'
          }
        }

        stage('build app') {
          agent {
            docker {
              image 'gradle:6-jdk11'
            }

          }
          steps {
            sh 'ci/build-app.sh'
          }
        }

      }
    }

  }
}