pipeline {
    agent any

    tools{
        maven "maven"
    }

    stages {

        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deploy on Ec-2'
            }
        }
    }
}
