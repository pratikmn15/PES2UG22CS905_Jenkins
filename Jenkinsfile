pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the project...'
                    sh 'make -C main' 
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    sh './hello_exec' 
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying the project...'
                    sh 'cp output /deploy/path/' 
                }
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
