pipeline {
    
    agent any
    
    tools {nodejs "Newman"}
    
    stages {
        
        stage("Install newman") {
        
            steps {
                sh 'npm install newman'
            }   
        }
        
        stage("test") {
        
            steps {
                sh 'newman run https://www.getpostman.com/collections/75b745addfbaa60a7121'
            }   
        }
        
        stage("deploy") {
        
            steps {
                echo 'deploying the application...'
            }   
        }
    }
}
