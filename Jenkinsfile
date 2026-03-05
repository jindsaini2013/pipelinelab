pipeline {
    agent any

    environment {
        GIT_URL = "https://github.com/kapilrahtor/Jenkins_pipeline.git"
        BRANCH_NAME = "main"
        APP_NAME = "DemoApp"
    }

    stages {

        stage('Clone Repository') {
            steps {
                echo "Cloning repository..."
                git branch: "${BRANCH_NAME}",
                    url: "${GIT_URL}"
            }
        }

        stage('Build') {
            steps {
                echo "Running Build Script..."
                bat "Build.bat"
            }
        }

        stage('Test') {
            steps {
                echo "Running Test Script..."
                bat "Test.bat"
            }
        }

        stage('Deploy') {
            when {
                expression {
                    currentBuild.currentResult == 'SUCCESS'
                }
            }
            steps {
                echo "Running Deployment Script..."
                bat "Deploy.bat"
            }
        }
    }

    post {
        success {
            echo "CI/CD Pipeline executed successfully 🎉"
        }
        failure {
            echo "Pipeline failed ❌"
        }
        always {
            echo "Execution completed."
        }
    }
}