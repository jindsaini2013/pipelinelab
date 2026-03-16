pipeline {
    agent any

    stages {
        stage('Pull from Git') {
            steps {
                // This pulls the latest code from your specific repo
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building...'
                // Ensure the script has execute permissions and run it
                sh 'chmod +x Build.sh'
                sh './Build.sh'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'chmod +x Test.sh'
                sh './Test.sh'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'chmod +x Deploy.sh'
                sh './Deploy.sh'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the logs above.'
        }
    }
}
