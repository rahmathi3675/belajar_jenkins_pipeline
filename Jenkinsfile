pipeline {
    agent any
    stages {
        stage("Hello") {
            steps {
                echo("Hello Pipeline")
            }
        }
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarScanner') { 
                    sh """
                        sonar-scanner \
                        -Dsonar.projectKey=belajar-pipeline \
                        -Dsonar.sources=.
                    """
                }
            }
        }
    }
}