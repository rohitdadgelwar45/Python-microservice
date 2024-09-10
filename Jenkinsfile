pipeline {
    agent any

    stages {
        stage('Prepare Environment') {
            steps {
                sh 'python3 --version || sudo apt-get install python3'
                sh 'pip3 --version || sudo apt-get install python3-pip'
            }
        }
        stage('Create Virtual Environment') {
            steps {
                sh 'python3 -m venv venv'
            }
        }
        stage('Install Flask') {
            steps {
                sh '''
                    source venv/bin/activate
                    pip install flask
                '''
            }
        }
    }
}
