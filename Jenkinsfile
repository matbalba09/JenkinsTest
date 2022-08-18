pipeline {
    
    agent any
    
    tools {nodejs "Newman"}
    
    stages {
        
        stage("Install newman") {
        
            steps {
                sh 'npm install'
            }   
        }
    }
}
