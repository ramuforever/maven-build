pipeline {
    agent any
    
    environment {
        // Define environment variables
        MAVEN_HOME = '/opt/maven'
        JAVA_HOME = '/usr/lib/jvm/java-8-openjdk-amd64'
    }

    stage('Checkout') {
    steps {
        // Replace 'your-git-repo-url' with the actual repo URL
        // If needed, add credentials or branch specification
        sh 'git clone https://github.com/ramuforever/maven-build.git'
            }
        }

        stage('Build') {
            steps {
                // Run Maven clean and compile
                sh '${MAVEN_HOME}/bin/mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                // Run unit tests using Maven
                sh '${MAVEN_HOME}/bin/mvn test'
            }
        }

        stage('Package') {
            steps {
                // Package the application as a JAR or WAR
                sh '${MAVEN_HOME}/bin/mvn package'
            }
        }

        stage('Deploy to Test Environment') {
            steps {
                // Simulate a deployment to a test environment
                echo 'Deploying to Test Environment...'
                // Example of a deploy step could be:
                // sh 'scp target/myapp.war user@test-server:/opt/tomcat/webapps/'
            }
        }
    }

    post {
        // Actions to take after the pipeline stages are completed
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
            // Actions to take after the build, regardless of success or failure
            echo 'Cleaning up workspace.'
            deleteDir()
        }
    }
}
