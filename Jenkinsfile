pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh '''
                python3 --version
                python3 -m pip install --upgrade pip --user || true
                python3 -m pip install --user -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                python3 -m pytest
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo Deployment successful!'
            }
        }
    }
}