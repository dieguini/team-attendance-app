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
        stage('Lint with flake8') {
            steps {
                sh """
                    # stop the build if there are Python syntax errors or undefined names
                    python3 -m flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics
                    # exit-zero treats all errors as warnings. The GitHub editor is 127 chars wide
                    python3 -m flake8 . --count --exit-zero --max-complexity=10 --max-line-length=127 --statistics
                """
            }
        }
        stage('Test with pytest') {
            steps {
                sh 'python3 -m coverage run -m pytest'
            }
        }
        stage('Coverage') {
            steps {
                sh 'python3 -m coverage html'
            }
        }
    }
}
