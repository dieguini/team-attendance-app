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
                sh 'python3 -m pip install --upgrade pip'
                sh 'pip install flake8 pytest'
                sh 'if [ -f requirements.txt ]; then pip install -r requirements.txt; fi'
            }
        }
    }
}
