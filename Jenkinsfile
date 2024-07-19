pipeline {
    agent any
    environment {
        GIT_REPO_URL = 'https://your.git.repo/url.git'
        BRANCH_NAME = 'main' // 你的分支名
        COMMIT_HASH = '' // 环境变量中的 commit hash，如果为空则拉取最新代码
    }
    stages {
        stage('Print Environment Variables') {
            steps {
                script {
                    sh 'printenv'
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                // 在这里添加你的构建命令，例如：sh 'make build'
            }
        }
    }
}
