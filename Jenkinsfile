pipeline {
    agent any

    tools {
        maven 'Maven 3'  // Name defined in Jenkins Global Tool Configuration
    }

    stages {
        stage('Clean') {
            steps {
                // Run Maven clean task to clean up the project
                echo 'Running Maven clean...'
                sh 'mvn clean'
            }
        }

        stage('Test') {
            steps {
                // Run Maven test task to run unit tests
                echo 'Running Maven test...'
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                // Run Maven package task to package the application (e.g., JAR/WAR)
                echo 'Running Maven package...'
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo 'Build, Test, and Package were successful!'
        }
        failure {
            echo 'Build failed. Please check the logs.'
        }
    }
}
