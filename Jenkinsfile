pipeline {
  agent any
  stages {
    stage('Deploy - Staging') {
      steps {
        echo "${env.HELLO}"
        echo './deploy staging'
        echo './run-smoke-tests'
        sh 'printenv'
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