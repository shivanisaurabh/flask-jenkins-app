pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh '''
                python3 --version

                curl -sS https://bootstrap.pypa.io/get-pip.py -o get-pip.py
                python3 get-pip.py --user --break-system-packages

                export PATH=$HOME/.local/bin:$PATH

                pip3 install --upgrade pip --break-system-packages
                pip3 install -r requirements.txt --break-system-packages
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                export PATH=$HOME/.local/bin:$PATH
                pytest
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