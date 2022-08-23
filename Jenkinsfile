pipeline {
    agent any
    
    tools {
        nodejs {'Newman'}
    }
    
    stages {
     

        
        stage ('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Newman Postman Test') {
            steps {
                bat 'newman run PostmanTest/RegressionTest.postman_collection.json -e PostmanTest/DevApi.postman_environment.json --disable-unicode'
            }
        }
    }
}
