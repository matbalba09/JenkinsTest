pipeline {
    agent { label 'LinuxSlave' }
    stages {
        stage ('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Test'){
            steps {
                sh 'npm install'
                sh 'npm run https://www.getpostman.com/collections/a27f66d0a51674259a0d'
                junit 'newman.xml'
            }
        }
    }
}
