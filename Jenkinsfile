pipeline {
    agent any

    environment {
        PROJECT_NAME = "multibranch-demo"
    }

    stages {

        stage('Preparation') {
            steps {
                echo "Building branch: ${env.PROD}"
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Running build for branch: ${env.PROD}"
                // Example build command
                sh 'echo "Simulating build process..."'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                // Example test command
                sh 'echo "Simulating tests..."'
            }
        }

        stage('Deploy') {
            when {
                anyOf {
                    branch 'main'
                    branch 'master'
                }
            }
            steps {
                echo "Deploying application for branch: ${env.BRANCH_NAME}"
                sh 'echo "Simulating deployment..."'
            }
        }
    }

    post {
        success {
            echo "✅ Build succeeded on branch: ${env.BRANCH_NAME}"
        }
        failure {
            echo "❌ Build failed on branch: ${env.BRANCH_NAME}"
        }
    }
}
