pipeline {
agent any

stages {

    stage('Job1 - Create JOB_1 directory') {
        steps {
            sh 'mkdir -p JOB_1'
        }
    }

    stage('Job2 - Create JOB_2 inside JOB_1') {
        steps {
            sh 'mkdir -p JOB_1/JOB_2'
        }
    }

    stage('Job3 - Create JOB_3 inside JOB_2') {
        steps {
            sh 'mkdir -p JOB_1/JOB_2/JOB_3'
        }
    }

}

}

