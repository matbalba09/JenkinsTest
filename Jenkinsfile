pipeline {
    
    agent any
    
    tools {nodejs "Newman"}
    
    stages {
    
        stage("Install Newman") {
        
            steps {
                sh "npm install -g newman"
            }   
        }
        
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
