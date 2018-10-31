pipeline {
  agent none
  stages {
    stage('DEV') {
      parallel {
        stage('DEV') {
          steps {
            echo 'This is my first DEV test'
          }
        }
        stage('Test-DEV') {
          steps {
            echo 'This is devtest'
          }
        }
      }
    }
  }
  environment {
    DEV = 'dev'
  }
}