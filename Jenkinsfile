pipeline {
    
    agent any
    
    tools {nodejs "Newman"}
    
    stages {
        
        stage ('Clean workspace') {
            steps {
                cleanWs()
            }
        }
        
        stage("Newman Run") {
        
            steps {
                sh 'newman run "RegressionTest.postman_collection.json"'
            }   
        }
    }
}
