pipeline {
    agent any
    stages {
        stage('sonar quality check') {
            agent {
                docker {
                    image 'maven:3.8.6-openjdk-17-slim'
                }
            }
            steps {
                script {
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                        sh "mvn clean package sonar:sonar"
                    }
                }
            }
        }
    }
}
