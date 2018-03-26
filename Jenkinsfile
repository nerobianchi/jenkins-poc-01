pipeline {
  agent any
  stages {
    stage('Deploy - Staging') {
      steps {
        echo 'HELLO'
        echo './deploy staging'
        echo './run-smoke-tests'
      }
    }
    stage('Sanity check') {
      steps {
        input 'Does the staging environment look ok?'
      }
    }
    stage('Deploy - Production') {
      steps {
        echo './deploy production'
      }
    }
  }
  environment {
    HELLO = 'world'
  }
}