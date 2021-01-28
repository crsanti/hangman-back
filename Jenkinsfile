pipeline {
    agent any
    stages {
        stage('audit tools') {
            steps {
                echo 'Pasando'
                // sh 'docker -v'
                // sh 'docker-compose -v'
            }
        }
        stage('unit test') {
            agent {
                docker {
                    image 'node:alpine3.12'
                }
            }
            steps {
                sh 'which node'
                sh 'which npm'
                sh 'node --version'
                sh 'npm --version'
                sh 'pwd'
                sh 'ls -l'
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
