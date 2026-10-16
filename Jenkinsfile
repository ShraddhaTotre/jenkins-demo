pipeline {

    agent any

    tools {
        maven 'Maven3'
        jdk 'JDK17'
    }

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
                sh 'mvn clean package'
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
