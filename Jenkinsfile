pipeline {
    
    agent any
    
    tools {
        nodejs
        {
            'Newman'
        }
    }
    
    stages {
        
        stage ('Clean workspace') {
            steps {
                cleanWs()
            }
        }
        
        stage("tests") {
        
            steps {
                sh 'newman run https://www.getpostman.com/collections/75b745addfbaa60a7121'
            }
        }
        
        stage("versions") {
        
            steps {
                sh 'node -v'
                sh 'npm -v'
            }   
        }
    }
}
