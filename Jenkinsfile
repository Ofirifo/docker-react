pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Ofirifo/docker-react.git'
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