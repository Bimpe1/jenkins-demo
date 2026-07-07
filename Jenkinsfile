pipeline {
    agent none

    stages {

        stage('Backend') {
            agent {
                docker {
                    image 'maven:3.9.6-eclipse-temurin-17'
                }
            }

            steps {
                sh 'mvn --version'
            }
        }

        stage('Frontend') {
            agent {
                docker {
                    image 'node:20-alpine'
                }
            }

            steps {
                sh 'node --version'
                sh 'npm --version'
            }
        }

    }
}
