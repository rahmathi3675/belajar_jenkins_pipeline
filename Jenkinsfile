pipeline {
    agent {
        node{
            label "linux"
        }
    }
    stages {

        stage("Build") {
            steps {
                echo("Start Build")
                sh("./mvnw clean compile test-compile")
                echo("Finish Build")
            }
        }

        stage("Test") {
            steps {
                echo("Start Build")
                sh("./mvnw test")
                echo("Finish Build")
            }
        }

        stage("Deploy") {
            steps {
                echo("Hello Deploy1")
                echo("Hello Deploy2")
                echo("Hello Deploy3")
            }
        }
    }
    post {
        always {
            echo "I will Always say Hello Again !"
        }
        success {
            echo "Yey, Success"
        }
        failure {
            echo "Oh No failure"
        }
        cleanup {
            echo "Dont't Care success or error"
        }
    }
}