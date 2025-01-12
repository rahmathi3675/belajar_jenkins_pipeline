pipeline {
    agent any
    tools {
        sonarqube "SonarScanner"
    }
    stages {
        stage("Hello") {
            steps {
                echo("Hello Pipeline")
            }
        }
        stage('SonarQube Analysis') {
            steps {
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