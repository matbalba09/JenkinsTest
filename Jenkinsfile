pipeline {
    agent any
    stages {
        
        stage ('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage ('Clean workspace') {
            steps {
                cleanWs()
            }
        }
        
        stage('Test') {
            steps {
                sh 'newman run PostmanTest/RegressionTest.postman_collection.json -e PostmanTest/DevApi.postman_environment.json'
            }
        }
    }
}
