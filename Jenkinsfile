pipeline {
    agent none
    environment {
        AUTHOR = "RAHMAT HIDAYAT"
        EMAIL = "rahmathi3675@gmail.com"
        WEB = "bukanprogrammer.com"
        APP = credentials("rahmat_rahasia")
    }
    parameters {
        string(name: "NAME", defaultValue: "Guest", description: "What is your name")
        text(name: "DESCRIPTION", defaultValue: "Guest", description: "Tell me you name ?" )
        booleanParam(name: "DEPLOY", defaultValue: "false", description: "Need a deploy ?" )
        choice(name: "SOCIAL_MEDIA", choices: ['Instagram','Facebook','Twitter'], description: "Which Social Media ?" )
        password(name: "SECRET", defaultValue: "", description: "Encrypt Key" )
    }
    options {
        disableConcurrentBuilds()
        timeout(time: 20, unit: 'SECONDS') 
    }
    stages {
        stage("Parameter") {
            agent {
                node{
                    label "linux && java17"
                }
            }
            steps {
              

                echo("Hello : ${params.NAME}")
                echo("Your Description Is : ${params.DESCRIPTION}")
                echo("Need to Deploy : ${params.DEPLOY}")
                echo("Social Media : ${params.SOCIAL_MEDIA}")
                echo("Your secret is : ${params.SECRET}")
            }
        }

        stage("Prepare") {
            agent {
                node{
                    label "linux || java17"
                }
            }
            steps {
                echo("App User : ${APP_USR}")
                //echo("App Password : ${APP_PSW}")
                sh("echo 'App Password : $APP_PSW' > 'rahasia.txt'")

                echo("Author : ${AUTHOR}")
                echo("Email : ${EMAIL}")
                echo("Web : ${WEB}")

                echo("Start Job : ${env.JOB_NAME}")
                echo("Start Build : ${env.BUILD_NUMBER}")
                echo("Branch Name : ${env.BRANCH_NAME}")
            }
        }

        stage("Build") {
            agent {
                node{
                    label "linux"
                }
            }
            steps {
                // GROOVY SCRIPT
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
            agent {
                node{
                    label "(windows && java17)"
                }
            }
            steps {

                // script {
                //     def data = [
                //         "firstName": : "Rahmat",
                //         "lastName": "Hidayat"
                //     ];
                //     writeJSON(file: "data.json", json: data);
                // }


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
            agent {
                node{
                    //label "(windows && java17) || linux"
                    label "linux"
                    //label "(windows && java17)"
                }
            }
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