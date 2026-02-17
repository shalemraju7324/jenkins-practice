pipeline {
    agent { label 'AGENT-1' }

    stages {

        stage('Build') {
            steps {
                echo 'Starting Build Stage...'
                sh 'echo "Compiling source code..."'
                sh 'sleep 2'
                echo 'Build completed successfully!'
            }
        }

        stage('Test') {
            steps {
                echo 'Starting Test Stage...'
                sh 'echo "Running tests..."'
                sh 'sleep 2'
                echo 'All tests passed!'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Starting Deploy Stage...'
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
