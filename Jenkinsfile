pipeline {
    agent any

    options {
        skipDefaultCheckout true
    }

    parameters {
        string(name: 'BRANCH', defaultValue: 'main', description: 'Branch to checkout')
        string(name: 'COMMIT_ID', defaultValue: '', description: 'Specific commit ID to checkout, leave empty for latest')
    }


    stages {
        stage('Print Environment Variables') {
            steps {
                script {
                    sh 'printenv'
                }
            }
        }
    }
}
