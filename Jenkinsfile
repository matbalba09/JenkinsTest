pipeline {
    
    agent any
        
    stages {
        
        stage ('Clean workspace') {
            steps {
                cleanWs()
            }
        }
        
        stage("Newman Run") {
        
            steps {
                sh 'npm install'
            }   
        }
    }
}
