pipeline {
    agent {
        node{
            label "windows && java17 || linux"
        }
    }
    stages {
        stage("Hello") {
            steps {
                echo("Hello Pipeline")
            }
        }
    }
}