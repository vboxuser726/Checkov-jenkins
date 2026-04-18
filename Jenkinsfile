pipeline {
    agent {label 'java'}

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/vboxuser726/Checkov-jenkins.git'
            }
        }

        stage('Install Checkov') {
            steps {
                sh '''
                pip3 install --upgrade checkov
                '''
            }
        }

        stage('Run Checkov Scan') {
            steps {
                sh '''
                checkov -d . --output cli
                '''
            }
        }
    }
}
