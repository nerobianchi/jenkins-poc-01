pipeline {
  agent none
  stages {
    stage('Back-end') {
      
      steps {
        sh 'echo hellow'
      }
    }
    stage 'Promotion' {
    timeout(time: 1, unit: 'HOURS') {
      input 'Deploy to Production?'
    }
  }
    stage('Front-end') {
      
      
     steps {
        sh 'echo hellowwwww'
      }
    }
  }
}
