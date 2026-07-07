pipeline {
    agent {
        docker {
            image 'python:3.11-slim'
            args '-u root -v /var/run/docker.sock:/var/run/docker.sock'
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

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-demo:${BUILD_NUMBER} .'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'python -m py_compile app.py'
            }
        }

    }
}
