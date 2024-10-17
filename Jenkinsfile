pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                sh 'git clone https://github.com/ramuforever/maven-build.git'
            }
        }

        stage('Build') {
            steps {
                // Run Maven clean and compile
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                // Run unit tests using Maven
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                // Package the application as a JAR or WAR
                sh 'mvn package'
            }
        }

        stage('Deploy to Test Environment') {
            steps {
                echo 'Deploying to Test Environment...'
                // Deployment steps can be added here
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }

        success {
            echo 'Pipeline succeeded.'
        }

        failure {
            echo 'Pipeline failed.'
        }

        cleanup {
            echo 'Cleaning up workspace.'
            deleteDir()
        }
    }
}
