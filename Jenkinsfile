pipeline {
    
    agent any
    
    tools {nodejs "Newman"}
    
    stages {
        
        stage("Newman Run") {
        
            steps {
                sh 'newman run RegressionTest.postman_collection.json'
            }   
        }
    }
}
