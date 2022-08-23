pipeline {

    agent any
    
    stages {
       
        stage('Clean Workspace'){
            steps {
            cleanWs()
            }
        }
         
        stage ('Checkout') {
            steps {
                checkout scm
            }
        }
        
    	stage('run Test newman') {
            steps {
                bat 'newman run PostmanTest/RegressionTest.postman_collection.json -e PostmanTest/DevApi.postman_environment.json -r junit,html --reporter-junit-export var/reports/newman/junit/newman.xml --reporter-html-export var/reports/newman/html/index.html --disable-unicode'
                junit "*.xml"
                  
                  
                publishHTML target: [
                    allowMissing: false,
                    alwaysLinkToLastBuild: false,
                    keepAll: true,
                    reportDir: '.',
                    reportFiles: 'newman_result.html',
                    reportName: 'Newman HTML Reporter'
                ]  
            }
        }
    }
}
