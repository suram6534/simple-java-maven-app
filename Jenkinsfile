pipeline {
    agent any

    environment {
        // Add this line to increase the heartbeat check interval
        MAVEN_OPTS = '-Dorg.jenkinsci.plugins.durabletask.BourneShellScript.HEARTBEAT_CHECK_INTERVAL=86400'
    }

    stages {
        stage('Checkout') {
            steps {
                git ''
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
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
