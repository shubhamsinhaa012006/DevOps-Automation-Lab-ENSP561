pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Build Stage Started'
                sh 'echo "Building Project..."'
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Test') {
            steps {
                echo 'Test Stage Started'
                sh 'echo "Running Tests..."'
                sh 'echo "Tests Passed Successfully"'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy Stage Started'
                sh 'echo "Deploying Application..."'
                sh 'echo "Deployment Successful"'
            }
        }
    }

    post {
        success {
            echo 'Pipeline Executed Successfully'
        }
    }
}