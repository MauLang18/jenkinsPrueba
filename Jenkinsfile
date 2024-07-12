pipeline {
    agent any

    environment {
        // Define las credenciales de Docker Hub
        DOCKER_HUB_CREDENTIALS = credentials('04be1968-514d-4aef-be55-93e4319a63d9')
    }

    stages {
        stage('docker build') {
            steps {
                script {
                    // Construye la imagen Docker
                    docker.build("maulang18/homer_page:1.0.0-${BUILD_ID}")
                }
            }
        }
        stage('docker push') {
            steps {
                script {
                    // Sube la imagen Docker a Docker Hub
                    docker.withRegistry('https://registry-1.docker.io/v2/', 'docker-hub-credentials') {
                        docker.image("maulang18/homer_page:1.0.0-${BUILD_ID}").push()
                    }
                }
            }
        }
    }
}
