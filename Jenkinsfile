pipeline {
    agent any
    stages {
        stage('Fetch dependencies') {
            steps {
                bat "echo 'My branch is: ${GIT_LOCAL_BRANCH}'"
                bat "cd 'C:\\Program Files (x86)\\Jenkins\\workspace\\test-pipeline\\my-app'"
                bat 'rmdir node_modules'
            }
        }
    }
}