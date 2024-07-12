pipeline {
    agent any

    stages {
        stage('docker build') {
            steps {
                script {
                    sh "docker build -t maulang18/homer_page:1.0.0-${BUILD_ID}"
                }
            }
        }
        stage('docker push') {
            steps {
                script {
                    sh "docker push maulang18/homer_page:1.0.0-${BUILD_ID}"
                }
            }
        }
    }
}