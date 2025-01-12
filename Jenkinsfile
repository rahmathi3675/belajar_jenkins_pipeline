pipeline {
    agent any
    stages {
        stage("Hello") {
            steps {
                echo("Hello Pipeline")
            }
        }
        stage('SonarQube Analysis') {
            def scannerHome = tool 'sonar';
            withSonarQubeEnv('sonar') { 
                sh "${scannerHome}/bin/sonar-scanner  --version"
            }
        }
    }
}