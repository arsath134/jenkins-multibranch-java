pipeline {

    agent any

    stages {

        stage('Build') {
            steps {
                echo "Building Java application..."
                bat 'javac src\\HelloWorld.java'
            }
        }

        stage('Test') {
            steps {
                echo "Running Java application..."
                bat 'java -cp src HelloWorld'
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }

            steps {
                echo "Deploying application from main branch..."
            }
        }
    }

    post {
        success {
            echo "Pipeline successful!"
            echo "Branch: ${env.BRANCH_NAME}"
        }

        failure {
            echo "Pipeline failed!"
            echo "Branch: ${env.BRANCH_NAME}"
        }
    }
}
