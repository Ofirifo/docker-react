pipeline {
    agent any
    parameters {
        choice(name: 'ENV', choices: ['dev', 'staging', 'prod'], description: 'Deploy environment')
    }

    stages {
        stage('Checkout') {
            steps {
             //   git branch: 'master', url: 'https://github.com/Ofirifo/docker-react.git'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building the app'
            }
        }
        stage('Deploy'){
            steps {
                sh "echo Deploying to ${params.ENV}"
            }
        }
        stage('Test') {
            steps {
                echo 'Running Tests'
            }
        }
    }
}