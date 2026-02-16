pipeline {
    agent any

    stages {
        stage('Build & Test') {
            agent {
                docker {
                    image 'maven:3.9.9-eclipse-temurin-17'
                }
            }
            steps {
                sh 'mvn clean verify'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}
