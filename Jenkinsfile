pipeline {
    agent { label 'agent-1' }

    environment {
        PROJECT = 'EXPENSE'
        COMPONENT = 'BACKEND'
    }

    options {
        disableConcurrentBuilds()
    }

    stages {

        stage('Build') {
            steps {
                echo "Starting Build Stage for ${PROJECT} ${COMPONENT}..."
                sh 'echo "Compiling source code..."'
                sh 'sleep 2'
                echo 'Build completed successfully!'
            }
        }

        stage('Test') {
            steps {
                echo "Starting Test Stage for ${PROJECT} ${COMPONENT}..."
                sh 'echo "Running tests..."'
                sh 'sleep 2'
                echo 'All tests passed!'
            }
        }

        stage('Deploy') {
            steps {
                echo "Starting Deploy Stage for ${PROJECT} ${COMPONENT}..."
                sh 'echo "Deploying application..."'
                sh 'sleep 2'
                echo 'Deployment successful!'
            }
        }

    }

    post {
        success {
            echo 'Pipeline completed successfully!'
            echo 'I will run when pipeline is success'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
