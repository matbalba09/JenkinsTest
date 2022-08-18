pipeline {
    
    agent any
    
    tools {nodejs "Newman"}
    
    stages {
    

        
        stage("test") {
        
            steps {
                sh 'newman run RegressionTest.postman_collection.json'
            }   
        }
        
        stage("deploy") {
        
            steps {
                echo 'deploying the application...'
            }   
        }
    }
}
