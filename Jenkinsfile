pipeline {
    agent any
    stages {
        stage('sonar quality check') {
            agent {
                docker {
                    image 'maven:3.8.6-openjdk-17'
                }
            }
            steps {
                script {
                    withSonarQubeEnv('sonar-server') {
                        sh "mvn clean package sonar:sonar"
                    }
                }
            }
        }
    }
}
