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
                }
            }
        }
        stage('Build') {
            steps {
                echo "Workspace directory during build: ${env.WORKSPACE_DIR}"
            }
        }
    }
    post {
        always {
            echo "Stashing workspace directory: ${env.WORKSPACE_DIR}"
        }
    }
}
