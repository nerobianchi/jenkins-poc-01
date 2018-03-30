pipeline {
  agent any
  stages {
    stage('Back-end') {
      steps {
        sh 'echo hellow'
      }
    }
    stage('Select deploy target') {
      steps {
        timeout(time: 5, unit: 'DAYS') {
            input message: 'Approve deployment?'
        }
      }
    }
    stage('Front-end') {
      steps {
        sh 'echo hellowwwww'
      }
    }
  }
}
