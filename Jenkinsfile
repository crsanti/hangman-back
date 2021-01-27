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
            // agent {
            //     docker {
            //         image 'node:alpine3.12'
            //     }
            // }
            steps {
                // echo 'run unit tests using Docker container base image'   
                // sh 'ls -l'
                // sh '$(npm bin)/jest --help'
                sh 'npm install'             
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
            cleanWs()
        }
    }
}