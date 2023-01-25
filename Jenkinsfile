pipeline {
  agent any
  stages {
    stage('Clone down') {
      agent {
        node {
          label 'master-label'
        }

      }
      steps {
        stash(excludes: '.git', name: 'Exclude .git file')
      }
    }

    stage('say hello') {
      parallel {
        stage('say hello') {
          steps {
            sh 'echo "Hello"'
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