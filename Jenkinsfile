pipeline {
    
    agent any
    
    tools {Nodejs "Newman"}
    
    stages {
        
        stage ('Clean workspace') {
            steps {
                cleanWs()
            }
        }
        
        stage("tests") {
        
            steps {
                sh 'node -v'
                sh 'npm -v'
                
            }   
        }
    }
}
