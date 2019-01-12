pipeline {
    agent any
    stages {
        stage('Fetch dependencies') {
            steps {
                bat "echo 'My branch is: ${env}'"
                bat 'rm -rf node_modules'
                nodejs('Node 8.12') {
                    bat 'npm install'
                }
            }
        }
    }
}