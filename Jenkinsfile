pipeline {
    agent any

    stages {
        stage('docker build') {
            steps {
                script {
                    bash "docker build -t maulang18/homer_page:1.0.0-${BUILD_ID}"
                }
            }
        }
        stage('docker push') {
            steps {
                script {
                    bash "docker push maulang18/homer_page:1.0.0-${BUILD_ID}"
                }
            }
        }
    }
}