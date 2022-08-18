pipeline {
    
    agent any
    
    stages {
    
        stage("build") {
        
            steps {
                echo 'building the application...'
            }   
        }
        
        stage("test") {
        
            steps {
                sh "newman run RegressionTest.postman_collection.json"
            }   
        }
        
        stage("deploy") {
        
            steps {
                echo 'deploying the application...'
            }   
        }
    }
}
