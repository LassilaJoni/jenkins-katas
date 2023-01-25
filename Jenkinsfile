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
          steps {
            sh 'echo "JOOOOOOOOOOOOO"'
          }
        }

      }
    }

    stage('Test app') {
      steps {
        unstash 'Restore'
        sh 'ci/unit-test-app.sh'
        sh 'junit \'app/build/test-results/test/TEST-*.xml\''
      }
    }

  }
}