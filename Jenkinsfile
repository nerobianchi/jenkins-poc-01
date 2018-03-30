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
        input 'Deploy?'
      }
    }
    stage('Front-end') {
      steps {
        sh 'echo hellowwwww'
      }
    }
  }
}