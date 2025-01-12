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
                withSonarQubeEnv('sonar') { 
                    sh "${scannerHome}/bin/sonar-scanner  --version"
                }
            }
        }
    }
}