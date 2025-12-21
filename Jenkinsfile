pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                Checkout sum
            }
        }
        stage('Build') {
            steps {
                echo 'Building the app'
            }
        }
        stage('Test') {
            steps {
                echo 'Running Tests'
            }
        }
    }
}