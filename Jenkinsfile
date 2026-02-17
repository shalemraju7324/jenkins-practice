pipeline {
    agent { label 'agent-1' }

    environment { 
        PROJECT = 'EXPENSE'
        COMPONENT = 'BACKEND' 
        DEPLOY_TO = "production"
    }

    options {
        disableConcurrentBuilds()
        timeout(time: 4, unit: 'MINUTES')
    }

    parameters{
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages {

        stage('Build') {
            steps {
               script {
                 sh """
                    echo "Hello, this is build"
                    echo "Project: ${env.PROJECT}"
                    echo "Component: ${env.COMPONENT}"

                    echo "Hello ${params.PERSON}"

                    echo "Biography: ${params.BIOGRAPHY}"

                    echo "Toggle: ${params.TOGGLE}"

                    echo "Choice: ${params.CHOICE}"

                    echo "Password received (hidden for security)"
                 """
               }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh """
                        echo "Hello, this is test"
                    """
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh """
                        echo "Hello, this is deploy"
                        echo "Deploying to ${env.DEPLOY_TO}"
                    """
                }
            }
        }

        stage('Parallel Stages') {
            parallel {

                stage('STAGE-1') {
                    steps {
                        script {
                            sh """
                                echo "Hello, this is STAGE-1"
                                sleep 15
                            """
                        }
                    }
                }

                stage('STAGE-2') {
                    steps {
                        script {
                            sh """
                                echo "Hello, this is STAGE-2"
                                sleep 15
                            """
                        }
                    }
                }

            }
        }

    }

    post { 
        always { 
            echo 'I will always say Hello again!'
        }

        failure { 
            echo 'I will run when pipeline is failed'
        }

        success { 
            echo 'I will run when pipeline is success'
        }
    }
}
