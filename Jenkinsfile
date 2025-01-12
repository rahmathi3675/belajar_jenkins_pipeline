pipeline {
    agent any
    tools {
        git 'Default'
    }
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
                        SonarScanner \
                        -Dsonar.projectKey=belajar-pipeline \
                        -Dsonar.sources=.
                    """
                }
            }
        }
    }
}