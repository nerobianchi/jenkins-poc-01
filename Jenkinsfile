pipeline {
    agent none
    stages {
        stage("Prepare build") {
            agent { any }
            steps {
                echo "prepare: ${pwd()}"
            }
        }
        stage("Build") {
            agent { any }
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
            agent { any }
            steps {
                echo "deploy: ${pwd()}"
            }
        }
    }
}
