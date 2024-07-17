pipeline {
    agent any

    environment {
        DOCKER_CREDENTIALS_ID = 'dockerhub-credentials-id' // Reemplaza con el ID de tus credenciales en Jenkins
        IMAGE_NAME = 'maulang18/homer_page'
        TAG = 'latest'
    }

    stages {
        stage('Docker Build') {
            steps {
                script {
                    sh "docker build -t ${IMAGE_NAME}:${TAG} ."
                }
            }
        }
        stage('Docker Push') {
            steps {
                script {
                    // Subir la imagen a Docker Hub
                    sh "docker push ${IMAGE_NAME}:${TAG}"
                }
            }
        }
        stage('Docker Compose Up') {
            steps {
                script {
                    dir('/path/to/docker/compose/files') {
                        sh 'docker-compose up -d'
                    }
                }
            }
        }
    }
}
