pipeline {
    
    agent {
        docker { 
            image 'postman/newman_ubuntu1404:2.1.2'
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
