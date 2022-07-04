pipeline {
    agent any

    stages {

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
