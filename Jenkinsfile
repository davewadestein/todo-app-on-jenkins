pipeline {
    agent any
    stages {
        stage('Compile') {
            steps {
                sh './gradlew clean compileJava'
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