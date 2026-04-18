pipeline {
    agent { label 'java' }

    stages {
        stage('Install Checkov') {
            steps {
                sh '''
                python3 -m pip install --upgrade checkov
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