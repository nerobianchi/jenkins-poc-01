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
              sh 'echo wait integration'
            }
            
          }
        }
        stage('acceptance') {
          steps {
            sh 'echo acceptance'
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