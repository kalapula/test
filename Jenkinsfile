pipeline {
    agent any
    stages {
        stage('Fetch dependencies') {
            steps {
                bat "echo 'My branch is: ${env}'"
                bat 'cd my-app'
                bat 'rmdir node_modules'
            }
        }
    }
}