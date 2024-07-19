pipeline {
    agent any

    environment {
        WORKSPACE_DIR = 'workspace'
    }


    stages {
        stage('Checkout') {
            steps {
                script {
                    echo "Workspace directory"
                }
            }
        }
        stage('Build') {
            steps {
                echo "Workspace directory during build"
            }
        }
    }
    post {
        always {
            echo "Stashing workspace directory"
        }
    }
}
