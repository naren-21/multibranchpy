pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'test123', url: 'https://github.com/naren-21/multibranchpy.git']]])
            }
        }
        stage('build') {
            steps {
                git branch: 'main', credentialsId: 'test123', url: 'https://github.com/naren-21/multibranchpy.git'
                sh 'python3 square.py'
            }
        }
        stage('print') {
            steps {
                echo "output printed"
            }
        )   
    }
}
