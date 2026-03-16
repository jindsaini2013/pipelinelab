pipeline {
agent any

```
stages {

    stage('Pull from Git') {
        steps {
            git 'https://github.com/jindsaini2013/pipelinelab.git'
        }
    }

    stage('Build') {
        steps {
            echo "Building the project..."
            sh 'echo Build Successful'
        }
    }

    stage('Test') {
        steps {
            echo "Running tests..."
            sh 'echo Tests Passed'
        }
    }

    stage('Deploy') {
        steps {
            echo "Deploying application..."
            sh 'echo Deployment Completed'
        }
    }

}
```

}

