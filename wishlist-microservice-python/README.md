pipeline {
    agent any

    stages {
        stage('Prepare Environment') {
            steps {
                // Install Python and pip (if not already available)
                sh 'python3 --version || sudo apt-get install python3'
                sh 'pip3 --version || sudo apt-get install python3-pip'
            }
        }
        stage('Create Virtual Environment') {
            steps {
                // Create a virtual environment (optional but recommended)
                sh 'python3 -m venv venv'
            }
        }
        stage('Install Flask') {
            steps {
                // Activate virtual environment and install Flask
                sh '''
                    source venv/bin/activate
                    pip install flask
                '''
            }
        }
    }
}
