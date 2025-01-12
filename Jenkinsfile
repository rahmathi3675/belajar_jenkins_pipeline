pipeline {
    agent {
        node{
            label "windows && java17"
        }
    }
    tools{
        git 'Default'
    }
    stages {
        stage("Hello") {
            steps {
                echo("Hello Pipeline")
            }
        }
    }
}