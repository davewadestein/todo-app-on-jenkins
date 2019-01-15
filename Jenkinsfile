pipeline {
    agent any
    stages {
        stage('Compile') {
            steps {
                sh './gradlew compileJava'
            }
        }
        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }
        stage('Integration Test') {
            steps {
                sh './gradlew integrationTest'
            }
        }
    }
}