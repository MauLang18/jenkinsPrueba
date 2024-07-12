pipeline {
    agent any

    stages {
        stage('docker build') {
            steps {
                script {
                    bat "docker build -t maulang18/homer_page:latest ."
                }
            }
        }
        stage('docker compose up') {
            steps {
                script {
                    dir('C:/Users/administrador/Desktop/Docker/Jenkins') {
                        bat 'docker-compose up -d'
                    }
                }
            }
        }
        stage('docker compose down') {
            steps {
                script {
                    dir('C:/Users/administrador/Desktop/Docker/Jenkins') {
                        bat 'docker-compose down'
                    }
                }
            }
        }
    }
}
