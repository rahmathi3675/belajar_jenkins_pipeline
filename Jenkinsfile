pipeline {
    agent {
        node{
            //label "(windows && java17) || linux"
            label "linux"
            //label "(windows && java17)"
        }
    }
    stages {

        stage("Build") {
            steps {

                script {
                    for( int i = 0; i < 10; i++){
                        echo("Script ${i}");
                    }
                }
                echo("Start Build")
                script {
                    if (isUnix()) {
                        // Untuk Linux
                        sh("./mvnw clean compile test-compile")
                    } else {
                        // Untuk Windows
                        bat("./mvnw clean compile test-compile")
                    }
                }
                echo("Finish Build")
            }
        }

        stage("Test") {
            steps {
                echo("Start Build")
                script {
                    if (isUnix()) {
                        // Untuk Linux
                        sh("./mvnw clean compile test-compile")
                    } else {
                        // Untuk Windows
                        bat("./mvnw clean compile test-compile")
                    }
                }
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