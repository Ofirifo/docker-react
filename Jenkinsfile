pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
             //   git branch: 'master', url: 'https://github.com/Ofirifo/docker-react.git'
                Checkout scm
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