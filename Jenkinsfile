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
                sh 'newman run PostmanTest/RegressionTest.postman_collection.json -e PostmanTest/DevApi.postman_environment.json'
            }
        }
    }
}
