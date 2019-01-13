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
                bat "echo ${GIT_BRANCH}"
                bat "echo 'workspace: ${workspace}'"
                bat "cd my-app && del /q node_modules"
                bat "git config --global url.'http://'.insteadOf git://"
            }
        }
        stage('Build') {
            steps {
                script {
                    switch(GIT_BRANCH) {
                        case "origin/develop":
                            result = "develop"
                            break
                        case "origin/master":
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
    post {
        success {
            // slackSend (color: '#00FF00', message: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
            bat "echo 'SUCCESSFUL: Job ${env.JOB_NAME} [${env.BUILD_NUMBER}] (${env.BUILD_URL})'"
        }
        failure {
            bat "echo 'FAILED: Job ${env.JOB_NAME} [${env.BUILD_NUMBER}] (${env.BUILD_URL})'"
        }

    }
}