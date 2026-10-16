pipeline {

    agent any

    environment {
        APP_NAME = "shopping-app"
    }

    parameters {
        string(name: 'ENV', defaultValue: 'dev')
    }

    options {
        timeout(time: 30, unit: 'MINUTES')
    }

    stages {

        stage('Build') {
            steps {
                echo "Building ${APP_NAME}"
            
            }
        }

        stage('Test') {
            steps {
                echo "Running Tests"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying to ${ENV}"
            }
        }
    }

    post {
        always {
            echo "Pipeline Finished"
        }

        success {
            echo "Build Successful"
        }

        failure {
            echo "Build Failed"
        }
    }
}
