pipeline {
    def scmVars = checkout scm
    def branchName = scmVars.GIT_BRANCH
    
    agent any
    stages {
        stage('Fetch dependencies') {
            steps {
                bat "echo 'My branch is: ${branchName}'"
                bat "cd 'C:\\Program Files (x86)\\Jenkins\\workspace\\test-pipeline\\my-app'"
                bat 'rmdir node_modules'
            }
        }
        stage('Build') {
            steps {
                bat "echo Building..."
            }
        }
        stage('Test') {
            steps {
                bat "echo Testing..."
            }
        }
        stage('Deploy') {
            steps {
                bat "echo Deploying..."
            }
        }
    }
}