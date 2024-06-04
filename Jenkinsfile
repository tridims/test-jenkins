/* Requires the Docker Pipeline plugin */
pipeline {
    agent { 
        docker { image 'golang:1.22.3-alpine3.20' } 
        label '!windows'
    }
    environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE    = 'sqlite'
    }
    stages {
        stage('build') {
            steps {
                sh 'go version'
                echo "Database engine is ${DB_ENGINE}"
                echo "DISABLE_AUTH is ${DISABLE_AUTH}"
                sh 'printenv'
            }
        }
    }
}


