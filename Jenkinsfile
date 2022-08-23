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
        
    	stage('run Test newman') {
            steps {
                bat 'newman run PostmanTest//RegressionTest.postman_collection.json -e PostmanTest//env//DevApi.postman_environment.json --disable-unicode'
            }
        }
    }
}
