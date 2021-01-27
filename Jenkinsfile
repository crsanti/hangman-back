pipeline {
    agent any
    stages {
        stage('audit tools') {
            steps {
                sh '''
                    docker -v
                    docker-compose -v
                '''
            }
        }
        stage('unit test') {
            // agent any
            docker {
                image 'node:alpine3.12'
            }
            steps {
                echo 'run unit tests using Docker container base image'                
                sh 'npm test'
            }
        }
        stage('integration test') {
            steps {
                echo 'run integartion tests with Docker compose'
            }
        }
    }
    post {
        always {
            echo 'clean resources'
        }
    }
}