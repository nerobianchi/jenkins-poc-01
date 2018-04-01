pipeline {
    agent none
    stages {
        stage("Prepare build") {
            agent { label 'some-agent' }
            steps {
                echo "prepare: ${pwd()}"
            }
        }
        stage("Build") {
            agent { label 'some-agent' }
            steps {
                parallel(
                    frontend: {
                        echo "frontend: ${pwd()}"
                    },
                    backend: {
                        echo "backend: ${pwd()}"
                    }
                )
            }
        }
       
        stage("Select deploy target") {
            agent none
            steps {
                input message: 'Deploy?'
            }
        }
        stage("Deploy") {
            agent { label 'some-agent' }
            steps {
                echo "deploy: ${pwd()}"
            }
        }
    }
}
