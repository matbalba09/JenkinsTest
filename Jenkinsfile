pipeline {
    
    agent any
    
    tools {
        nodejs
        {
            "Newman"
        }
    }
    
    stages {
        
        stage ('Clean workspace') {
            steps {
                cleanWs()
            }
        }
        
        stage("versions") {
        
            steps {
                sh "npm install"
            }   
        }
        
        stage("tests") {
        
            steps {
                sh "newman run https://www.getpostman.com/collections/75b745addfbaa60a7121"
            }
        }
    }
}
