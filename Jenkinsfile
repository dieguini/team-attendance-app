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
        //stage('Install dependencies') {
        //    steps {
        //        sh 'python -m pip install --upgrade pip'
        //        sh 'pip install flake8 pytest'
        //        sh 'if [ -f requirements.txt ]; then pip install -r requirements.txt; fi'
        //    }
        //}
    }
}
