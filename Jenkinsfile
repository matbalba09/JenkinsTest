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

        node('ts-build') {
            def collectionName = 'https://www.getpostman.com/collections/75b745addfbaa60a7121'
            docker.image('postman/newman_ubuntu1404').inside("--entrypoint=''")
            {
                sh "newman run '$collectionName'"
            }
        }
    }
}
