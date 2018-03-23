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
            echo 'integration'
          }
        }
        stage('acceptance') {
          steps {
            sh 'echo acceptanceeeee'
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
        input(message: 'Are you sure want to deploy to PROD', id: '1', ok: 'OK', submitter: 'admin')
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