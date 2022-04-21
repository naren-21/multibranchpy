pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/python']], extensions: [], userRemoteConfigs: [[credentialsId: 'test123', url: 'https://github.com/naren-21/multibranchpy.git']]])
            }
        }
        stage('build') {
            steps {
                git branch: 'python', credentialsId: 'test123', url: 'https://github.com/naren-21/multibranchpy.git'
                sh 'python3 square.py'
            }
        }
        stage('thanks') {
            steps {
                echo "thank you"
            }
        )   
    }
}
