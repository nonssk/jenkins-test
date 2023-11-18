pipeline {
    agent any

    tools {
        nodejs 'node_18_16_0'
    }

    environment {
        PROJECT_NAME = 'test'
    }

    stages {
        stage('Install') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }
        stage('check version') {
            steps {
                script {
                    def version = sh(script: 'node -pe "require(\'./package.json\').version"', returnStdout: true).trim()
                    env.VERSION = version
                    echo "Install project ${PROJECT_NAME} version ${env.VERSION}"
                }
            }
        }
    }
}

