pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://gitlab.com/HarishKM7/multi-tiered-web-app']]])
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
