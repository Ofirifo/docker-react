pipeline {
    agent {
        docker {
            image 'node:18'
        }
    }
    parameters {
        choice(name: 'ENV', choices: ['dev', 'staging', 'prod'], description: 'Deploy environment')
    }

    stages {
        stage('Install') {
            steps {
                sh 'npm --version'
                sh 'npm install'
            }
        }
        stage('Checkout') {
            steps {
             //   git branch: 'master', url: 'https://github.com/Ofirifo/docker-react.git'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'npm install && npm run build'
                echo 'Building the app'
            }
        }
        stage('Deploy'){
            steps {
                sh "echo Deploying to ${params.ENV}"
            }
        }
        stage('Approve Production') {
            when {
                expression { params.ENV == 'prod' }
            }
            steps {
                timeout(time: 30, unit: 'MINUTES') {
                    input message: 'Deploy to PRODUCTION?', ok: 'Deploy'
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Running Tests'
            }
        }
    }
    
    post {
        success {
            echo 'Build succeeded'
        }
        failure {
            echo 'Build failed'
        }
        always {
            cleanWs()
        }
    }
}