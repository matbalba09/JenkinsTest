pipeline {
    agent any
    
    tools {
        nodejs
        {
            'Newman'
        }
    }
    
    stage ('Clean workspace') {
            steps {
                cleanWs()
            }
        }
    
    stages {
        
        stage ('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Test') {
            steps {
                bat 'newman run PostmanTest/RegressionTest.postman_collection.json -e PostmanTest/DevApi.postman_environment.json'
            }
        }
    }
}
