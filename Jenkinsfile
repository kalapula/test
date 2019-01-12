def scmVars = checkout scm
def branchName = scmVars.GIT_BRANCH

pipeline {
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
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}