pipeline {
    agent any

    stages {
        stage('Install Python') {
            steps {
                sh """
                    sudo apt update
                    sudo apt install python3-pip -y
                """
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'python3 -m pip3 install --upgrade pip'
                sh 'pip3 install flake8 pytest'
                sh 'if [ -f requirements.txt ]; then pip3 install -r requirements.txt; fi'
            }
        }
    }
}
