pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Starting Build Stage...'
                
                // Example build command
                sh 'echo "Compiling source code..."'
                
                // simulate build
                sh 'sleep 2'
                
                echo 'Build completed successfully!'
            }
        }

        stage('Test') {
            steps {
                echo 'Starting Test Stage...'
                
                // Example test command
                sh 'echo "Running tests..."'
                
                // simulate testing
                sh 'sleep 2'
                
                echo 'All tests passed!'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Starting Deploy Stage...'
                
                // Example deploy command
                sh 'echo "Deploying application..."'
                
                // simulate deployment
                sh 'sleep 2'
                
                echo 'Deployment successful!'
            }
        }

    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
