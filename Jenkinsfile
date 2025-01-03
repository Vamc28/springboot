pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh './mvnw clean install'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh './mvnw test'
                }
            }
        }
        stage('Package') {
            steps {
                script {
                    sh './mvnw package'
                }
            }
        }
    }
}
