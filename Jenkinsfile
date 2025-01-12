pipeline {
    agent any
    tools {
        sonarqube 'SonarScanner' // Nama scanner yang Anda konfigurasi di Jenkins
    }
    stages {
        stage("Hello") {
            steps {
                echo("Hello Pipeline")
            }
        }
        stage('SonarQube Analysis') {
            steps {
                // Gunakan environment SonarQube yang dikonfigurasi di Jenkins
                withSonarQubeEnv('SonarQube') { 
                    sh """
                        sonar-scanner \
                        -Dsonar.projectKey=<TEST> \
                        -Dsonar.sources=.
                    """
                }
            }
        }
    }
}