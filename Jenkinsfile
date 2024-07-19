pipeline {
    agent any
    environment {
        GIT_REPO = 'git@github.com:xurunjie/test.git'
        BRANCH = 'main'
    }
    stages {
        stage('Checkout or Pull SCM') {
            steps {
                script {
                    // 检查工作空间是否已经有.git目录
                    if (fileExists('.git')) {
                        echo 'Repository exists, pulling latest changes'
                        sh '''
                            git reset --hard
                            git clean -fd
                            git pull origin ${BRANCH}
                        '''
                    } else {
                        echo 'Repository does not exist, cloning'
                        sh '''
                            git clone ${GIT_REPO} .
                            git checkout ${BRANCH}
                        '''
                    }
                }
            }
        }
        // 其他的阶段可以在这里定义
        stage('Build') {
            steps {
                echo 'Building...'
                // 构建步骤
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // 测试步骤
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // 部署步骤
            }
        }
    }
}
