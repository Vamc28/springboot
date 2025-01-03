pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout scm
                }
            }
        }

        stage('Build and Test') {
            steps {
                script {
                    // Navigate to the directory containing your project
                    dir('/var/lib/jenkins/workspace/pipeline-testing_main') {
                        // Run mvn clean install inside the specified directory
                        sh 'mvn clean install'
                    }
                }
            }
        }
    }
}
