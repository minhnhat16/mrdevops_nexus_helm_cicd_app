pipeline {
    agent any
    stages {
        stage('sonar quality check') {
            agent {
                docker {
                    image 'maven'
                }
            }
            steps {
                script {
                    def localRepoPath = "src/main/java/com/.m2/repository"
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                        sh "mvn clean package sonar:sonar -Dmaven.repo.local=${localRepoPath}"
                    } 
                }
            }
        }
    }
}
