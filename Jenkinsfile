pipeline {
    
    agent any
    
    stages {
        
        stage ('Clean workspace') {
            steps {
                cleanWs()
            }
        }
        
        stage("versions") {
        
            steps {
                sh 'node -v'
                sh 'npm -v'
            }   
        }
        
        stage("tests") {
        
            steps {
                sh 'newman -u https://www.getpostman.com/collections/75b745addfbaa60a7121;'
            }
        }
    }
}
