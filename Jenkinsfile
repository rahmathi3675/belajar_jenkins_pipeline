pipeline {
    agent {
        node{
            label "(windows && java17) || linux"
        }
    }
    stages {

        stage("Build") {
            steps {
                echo("Hello Build1")
                sleep(10)
                echo("Hello Build2")
                echo("Hello Build3")
            }
        }

        stage("Test") {
            steps {
                echo("Hello Test1")
                sleep(10)
                echo("Hello Test2")
                echo("Hello Test3")
                //sh "error"
            }
        }

        stage("Deploy") {
            steps {
                echo("Hello Deploy1")
                sleep(10)
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