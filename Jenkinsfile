pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Get some code from a GitHub repository
                checkout scm
            }
        }
        stage('Build image') {
            steps {
                script {
                       img = docker.build 'azitmentor/sample2','./cicdtest'
                }
            }
        }
        stage('Push to docker') {
            steps {
                script {
                    docker.withRegistry("https://index.docker.io/v1/","docker") {
                       img.push()
                    }
                }
            }
        }
    }
}
