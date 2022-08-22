pipeline {
    
    agent any
    
    stages {
        
        stage ('Clean workspace') {
            steps {
                cleanWs()
            }
        }
        
        stage ('Git Checkout') {
            steps {
                git branch: "develop", url: "https://github.com/matbalba09/JenkinsTest.git"
            }
        }
        
        stage("npm install") {
        
            steps {
                sh "npm install"
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
