pipeline {

    agent any
    
    stages {
       
        stage('Clean Workspace'){
            steps {
            cleanWs()
            }
        }
         
        stage ('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage("Install newman") {
        
            steps {
                bat 'npm install -g newman'
            }   
        }
        
        stage('AdminService Test') {
            steps {
                bat 'newman run AdminService/RegressionTest.postman_collection.json -e AdminService/env/DevApi.postman_environment.json --disable-unicode'
            }
        }
        
    	stage('DocStoreService Test') {
            steps {
                bat 'newman run DocStoreService/RegressionTest.postman_collection.json -e DocStoreService/env/DevApi.postman_environment.json --disable-unicode'
            }
        }
    }
}
