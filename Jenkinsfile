pipeline {
    agent {
        docker {
            image 'python:3.11-slim'
        }
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out code...'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Build') {
            steps {
                sh 'python --version'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'python -m py_compile app.py'
            }
        }
    }
}
