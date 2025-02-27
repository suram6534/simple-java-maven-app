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

    post {
        success {
            echo 'Build, Test, and Package were successful!'
        }
        failure {
            echo 'Build failed. Please check the logs.'
        }
    }
}
