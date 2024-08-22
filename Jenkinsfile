pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning the repository...'
                git branch: 'main', url: 'https://github.com/talelekaustubh/jpypi.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the Java project...'
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging the application...'
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Simulating deployment
                sh 'echo "Deploying to production..."'
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
            cleanWs()
        }

        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Please check the logs.'
        }
    }
}