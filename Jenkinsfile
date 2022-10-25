pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Install dependencies') {
            steps {
                python -m pip install --upgrade pip
                pip install flake8 pytest
                if [ -f requirements.txt ]; then pip install -r requirements.txt; fi
            }
        }
    }
}
