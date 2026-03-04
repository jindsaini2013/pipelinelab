pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Cloning the repository..."
                git url: 'https://github.com/kapilrahtor/Jenkins_pipeline.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                echo "Building the application..."
                bat 'echo Building app...'
		bat 'Build.bat'
                bat 'timeout /t 2 >nul'
                bat 'echo Build completed!'
            }
        }

        stage('Unit Test') {
            steps {
                echo "Running unit tests..."
                bat 'echo Running tests...'
		bat 'Unit.bat'
                bat 'timeout /t 2 >nul'
                bat 'echo All tests passed!'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application..."
                bat 'echo Deploying app...'
		bat 'Deploy.bat'
                bat 'timeout /t 2 >nul'
                bat 'echo Deployment successful!'
            }
        }
    }

    post {
        success {
            echo "Pipeline finished successfully!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}