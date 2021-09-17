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
                    docker.build("suneel35/mtwa-webserver", "-f Dockerfile.webserver .")
                    docker.build("suneel35/mtwa-appserver", "-f Dockerfile.appserver .")
                    docker.build("suneel35/mtwa-mysql", "-f Dockerfile.mysql .")
                }
            }
        }
    }
}
