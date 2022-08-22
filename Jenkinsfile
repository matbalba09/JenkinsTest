pipeline {
    
    agent any
    
    node {
        env.PATH="${env.NODEJS_HOME}/bin:${env.PATH}"
    }
    
    stages {
        
        stage ('Clean workspace') {
            steps {
                cleanWs()
            }
        }
        
        stage("npm install") {
        
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
