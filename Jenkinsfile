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
                        -Dsonar.projectKey=belajar-pipeline \
                        -Dsonar.sources=.
                    """
                }
            }
        }
    }
}