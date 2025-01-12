pipeline {
    agent {
        node{
            label "windows && java17 || linux"
        }
    }
    stages {

        stage("Build") {
            steps {
                echo("Hello Build")
            }
        }

        stage("Test") {
            steps {
                echo("Hello Test")
            }
        }

        stage("Deploy") {
            steps {
                echo("Hello Deploy")
            }
        }

        stage("Hello") {
            steps {
                echo("Hello Pipeline")
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