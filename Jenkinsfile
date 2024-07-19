pipeline {
    agent any
    stages {
        stage('Checkout SCM') {
            steps {
                script {
                    // 拉取指定的提交
                    checkout([
                        $class: 'GitSCM',
                        branches: [[name: 'main']],
                        userRemoteConfigs: [[url: 'git@github.com:xurunjie/test.git']],
                        extensions: [
                            [$class: 'CloneOption', shallow: true, depth: 1, noTags: true],
                            [$class: 'RelativeTargetDirectory', relativeTargetDir: 'repo']
                        ]
                    ])
                }
            }
        }
        stage('Build') {
            steps {
                // 构建步骤
                echo 'Building...'
            }
        }
    }
}
