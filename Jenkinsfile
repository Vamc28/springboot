pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh './mvn clean install'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh './mvn test'
                }
            }
        }
        stage('Package') {
            steps {
                script {
                    sh './mvn package'
                }
            }
        }
    }
}
