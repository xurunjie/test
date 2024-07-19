pipeline {
    agent any

    environment {
        WORKSPACE_DIR = 'workspace'
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    echo "Workspace directory: ${env.WORKSPACE_DIR}"
                    
                    if (!fileExists("${env.WORKSPACE_DIR}/.git")) {
                        // Initial checkout
                        dir(env.WORKSPACE_DIR) {
                            checkout scm
                        }
                        stash name: 'workspace', includes: "${env.WORKSPACE_DIR}/**/*"
                    } else {
                        // Restore from stash and pull latest changes
                        unstash 'workspace'
                        dir(env.WORKSPACE_DIR) {
                            sh 'git pull'
                        }
                    }
                }
            }
        }
        stage('Build') {
            steps {
                echo "Workspace directory during build: ${env.WORKSPACE_DIR}"
                dir(env.WORKSPACE_DIR) {
                    // Your build steps here
                    sh 'make build'
                }
            }
        }
    }
    post {
        always {
            echo "Stashing workspace directory: ${env.WORKSPACE_DIR}"
            stash name: 'workspace', includes: "${env.WORKSPACE_DIR}/**/*"
        }
    }
}
