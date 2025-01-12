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
                withSonarQubeEnv('SonarQube') { 
                    sh """
                        sonar-scanner \
                        -Dsonar.projectKey=belajar_jenkins-pipeline \
                        -Dsonar.sources=.
                    """
                }
            }
        }
    }
}