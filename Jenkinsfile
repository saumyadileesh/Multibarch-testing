pipeline {
    agent any

    environment {
        PROJECT_NAME = "multibranch-test-demo"
    }

    stages {

        stage('Preparation') {
            steps {
                echo "Building branch: ${env.dev}"
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Running build for branch: ${env.dev}"
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
                    branch 'dev'
                    branch 'dev'
                }
            }
            steps {
                echo "Deploying application for branch: ${env.dev}"
                sh 'echo "Simulating deployment..."'
            }
        }
    }

    post {
        success {
            echo "✅ Build went succeeded on branch: ${env.BRANCH_NAME}"
        }
        failure {
            echo "❌ Build failed on branch: ${env.BRANCH_NAME}"
        }
    }
}
