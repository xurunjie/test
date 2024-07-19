pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                echo 'venv venv'
                checkout scm
            }
        }
        
        stage('Set Up Environment') {
            steps {
                // Set up Python environment
                echo 'python3 -m venv venv'
                echo 'source venv/bin/activate'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install dependencies
                echo 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                // Run tests
                echo 'pytest'
            }
        }
    }

    post {
        always {
            // Clean up environment
            echo 'deactivate'
            cleanWs()
        }
    }
}
