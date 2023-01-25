pipeline {
  agent any
  stages {
    stage('Clone down') {
      steps {
        echo 'Hello'
      }
    }

    stage('say hello') {
      parallel {
        stage('say hello') {
          steps {
            sh 'echo "Hello"'
          }
        }

        stage('') {
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