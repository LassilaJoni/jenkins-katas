pipeline {
  agent any
  stages {
    stage('Parallel execution') {
      parallel {
        stage('Parallel execution') {
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

    stage('Echo') {
      steps {
        sh 'echo "Hello world"'
      }
    }

  }
}