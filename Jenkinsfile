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
              script {
                return true
              }
              
            }
            
          }
        }
        stage('acceptance') {
          steps {
            sh 'echo acceptanceeeee'
          }
        }
        stage('My throttled build') {
          steps {
            throttle(categories: ['throttleDocker']) {
              node(label: 'docker') {
                sh 'sleep 1'
                echo 'Done'
              }
              
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
  post {
    always {
      cleanWs()
      
    }
    
  }
  options {
    timeout(time: 60, unit: 'MINUTES')
  }
}