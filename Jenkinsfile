pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo \'build\''
      }
    }
    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sh 'echo \'test\''
          }
        }
        stage('integration') {
          steps {
            waitUntil() {
              sh 'true'
            }
            
          }
        }
        stage('acceptance') {
          steps {
            withEnv(overrides: ['MYTOOL_HOME=acceptance']) {
              sh 'echo $MYTOOL_HOME'
            }
            
          }
        }
      }
    }
    stage('deploy to test') {
      steps {
        sh 'echo \'deploy to test\''
      }
    }
    stage('deploy to qa') {
      steps {
        sh 'echo \'deploy to qa\''
      }
    }
    stage('deploy to prod') {
      steps {
        sh 'echo \'deploy to prod\''
      }
    }
  }
  environment {
    asdfg = '123'
  }
}