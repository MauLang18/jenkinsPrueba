pipeline {
    agent any

    stages {
        stage('docker build') {
            steps {
                script {
                    bat "docker build -t maulang18/homer_page:1.0.0-${BUILD_ID} ."
                }
            }
        }
        stage('docker run') {
            steps {
                script {
                    bat "docker run -d -p 10108:80 maulang18/homer_page:1.0.0-${BUILD_ID}"
                }
            }
        }
    }
}