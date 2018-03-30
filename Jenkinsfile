pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo Building'
      }
    }
    stage('Select deploy target') {
      parallel {
        stage('Integration Tests') {
          steps {
            timeout(time: 5, unit: 'DAYS') {
              input 'Approve deployment?'
            }
            
          }
        }
        stage('Acceptance Tests') {
          steps {
            timeout(time: 5, unit: 'DAYS') {
              input 'sure?'
            }
            
          }
        }
      }
    }
    stage('Deploy to Test') {
      steps {
        sh 'echo Deploy to testing'
      }
    }
    stage('Deploy to QA') {
      steps {
        timeout(time: 5, unit: 'DAYS') {
          input 'Deploy to QA?'
        }
        
      }
    }
    stage('Deploy to Prod') {
      steps {
        timeout(time: 5, unit: 'DAYS') {
          input 'Deploy to Prod?'
        }
        
      }
    }
  }
}