pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {

        stage('Build') {
            steps {
                echo '===== BUILD STAGE ====='
                sh 'echo "Building Application..."'
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Test') {
            steps {
                echo '===== TEST STAGE ====='
                sh 'echo "Running Test Cases..."'
                sh 'echo "All Tests Passed"'
            }
        }

        stage('Deploy') {
            steps {
                echo '===== DEPLOY STAGE ====='
                sh 'mkdir -p deployment'
                sh 'echo "Application Deployed Successfully" > deployment/status.txt'
                sh 'cat deployment/status.txt'
            }
        }
    }

    post {

        success {
            echo 'Deployment Successful!'
        }

        failure {
            echo 'Deployment Failed!'
        }

        always {
            echo 'Pipeline Execution Finished'
        }
    }
}