pipeline {
    agent any

    stages {
        stage('Checkout from GitHub') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/yuvrajjdamdar4-png/set5-devops.git'
            }
        }

        stage('Build Docker image') {
            steps {
                sh 'docker build -t set5-app:$BUILD_NUMBER .'
            }
        }

        stage('Ansible health check') {
            steps {
                sh 'ansible localhost -i localhost, -m ping -c local'
            }
        }
    }
}
