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
                bat "cd '${JENKINS_HOME}\\my-app'"
                bat 'rmdir node_modules'
            }
        }
        stage('Build') {
            steps {
                bat "echo ''########## BUILD ##########'"
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