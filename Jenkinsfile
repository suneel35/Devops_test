pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/suneel35/Devops_test.git'
            }
        }
        stage('Docker Builds') {
            steps {
                script {
                    docker.build("kmharish/mtwa-webserver", "-f Dockerfile.webserver .")
                    docker.build("kmharish/mtwa-appserver", "-f Dockerfile.appserver .")
                    docker.build("kmharish/mtwa-mysql", "-f Dockerfile.mysql .")
                }
            }
        }
    }
}
