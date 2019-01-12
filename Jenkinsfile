pipeline {
    agent any
    stages {
        stage('Fetch dependencies') {
            steps {
                sh "echo 'My branch is: ${env.BRANCH_NAME}'"
                sh 'rm -rf node_modules'
                nodejs('Node 8.12') {
                    sh 'npm install'
                }
            }
        }
    }
}