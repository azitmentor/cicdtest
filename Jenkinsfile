pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                checkout scm

                script {
                    docker.withRegistry("https://index.docker.io/v1/","docker") {
                       def img = docker.build 'azitmentor/sample2','./cicdtest'
                       img.push()
                    }
                }
            }
        }
    }
}
