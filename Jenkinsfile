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
        always {

            bat "echo '${GIT_BRANCH}'"
            bat "echo '${GIT_URL}'"
            bat "echo '${GIT_COMMIT}'"
            bat "echo 'git show -s --pretty=%an'"

            // slackSend channel: '#admin',
            //     color: COLOR_MAP[currentBuild.currentResult],
            //     message: "*${currentBuild.currentResult}:* Job ${env.JOB_NAME} build ${env.BUILD_NUMBER} by ${BUILD_USER}\n More info at: ${env.BUILD_URL}" 
        }
    }
}