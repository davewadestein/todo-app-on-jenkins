pipeline {
    agent any
    stages {
        stage('Compile') {
            steps {
                sh './gradlew clean compileJava'
            }
        }
        stage('All Tests') {
            parallel {
                stage('Test') {
                    steps {
                        sh './gradlew test'
                    }
                    post {
                        always {
                            junit '**/build/test-results/test/TEST-*.xml'
                        }
                    }
                }
                stage('Integration Test') {
                    steps {
                        sh './gradlew integrationTest'
                    }
                    post {
                        always {
                            junit '**/build/test-results/integrationTest/TEST-*.xml'
                        }
                    }
                }
            }
        }
    }
}