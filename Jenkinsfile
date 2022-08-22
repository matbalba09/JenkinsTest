pipeline {
    
    agent any
    
    stages {
        
        stage ('Clean workspace') {
            steps {
                cleanWs()
            }
        }
        
        stage("npm install") {
        
            steps {
                sh "npm config ls"
            }   
        }
        
        stage("tests") {
        
            steps {
                sh "newman run https://www.getpostman.com/collections/75b745addfbaa60a7121"
            }
        }
    }
}
