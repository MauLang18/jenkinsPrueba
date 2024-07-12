pipeline {
    agent any
    stages {
        stage('Declarative: Checkout SCM') {
            steps {
                checkout scm
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'docker build -t mi-imagen .'
                    } else {
                        bat 'docker build -t mi-imagen .'
                    }
                }
            }
        }
        stage('Push Docker Image') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'docker push mi-imagen'
                    } else {
                        bat 'docker push mi-imagen'
                    }
                }
            }
        }
    }
}
