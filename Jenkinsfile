pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh '''
                python3 --version

                # Install pip manually
                curl -sS https://bootstrap.pypa.io/get-pip.py -o get-pip.py
                python3 get-pip.py --user

                # Add pip to PATH
                export PATH=$HOME/.local/bin:$PATH

                pip3 install --upgrade pip
                pip3 install -r requirements.txt
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