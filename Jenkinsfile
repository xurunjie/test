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
                    bat 'set'
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                // 在这里添加你的构建命令，例如：bat 'make build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // 在这里添加你的测试命令，例如：bat 'make test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // 在这里添加你的部署命令，例如：bat 'make deploy'
            }
        }
    }
}