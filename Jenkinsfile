pipeline {
    agent any

    environment {
        MAVEN_HOME = tool 'Maven_3' // Assuming you've configured Maven in Jenkins Global Tools
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the current branch
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Run Maven build command
                script {
                    sh "'${MAVEN_HOME}/bin/mvn' clean install -DskipTests"
                }
            }
        }

        stage('Test') {
            steps {
                // Run unit tests
                script {
                    sh "'${MAVEN_HOME}/bin/mvn' test"
                }
            }
        }

        stage('Package') {
            steps {
                // Package the Spring Boot app
                script {
                    sh "'${MAVEN_HOME}/bin/mvn' package"
                }
            }
        }

        stage('Deploy') {
            steps {
                // Deploy your app or push to a container registry (for example)
                echo 'Deploying the application (Optional)'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }

        failure {
            echo 'Build failed. Please check the logs.'
        }
    }
}
