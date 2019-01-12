pipeline {  
    agent any
    stages {
        stage('Fetch dependencies') {
            steps {
                bat "echo '########## FETCH DEPENDENCIES ##########'"
                script {
                    scmVars = checkout scm
                    branchName = scmVars.GIT_BRANCH
                    workspace = pwd()
                }
                bat "echo 'My branch is: ${branchName}'"
                bat "echo 'workspace: ${workspace}'"
                bat "cd my-app && del /q node_modules"
            }
        }
        stage('Build') {
            steps {
                script {
                    switch(branchName) {
                        case "develop":
                            result = "develop"
                            break
                        case ["master"]:
                            result = "master"
                            break
                        default:
                            result = "def"
                            break
                    }
                }
                bat "echo 'result: ${result}'"
            }
        }
        stage('Test') {
            steps {
                bat "echo '########## TEST ##########'"
            }
        }
        stage('Deploy') {
            steps {
                bat "echo '########## DEPLOY ##########'"
            }
        }
    }
}