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
        
//         stage("Install newman") {
        
//             steps {
//                 bat 'npm install newman'
//             }   
//         }
        
        stage('AdminService Test') {
            steps {
                bat 'newman run AdminService/RegressionTest.postman_collection.json -e AdminService/env/DevApi.postman_environment.json -r htmlextra --reporter-htmlextra-export ./results/report.html'
            
                publishHTML (target: [
                allowMissing: false, 
                alwaysLinkToLastBuild: true, 
                keepAll: false, 
                reportDir: 'C:\Users\Mat\.jenkins\workspace\tman_Test_Github_Pipeline3_dev_2\results', 
                reportFiles: 'report.html', 
                reportName: 'Newman HTML Report', 
                reportTitles: ''
                ])
            }
            
            
//             steps {
//                 bat 'newman run AdminService/RegressionTest.postman_collection.json -e AdminService/env/DevApi.postman_environment.json -reporters cli,junit,html --reporter-junit-export "newman/myreport.xml" --reporter-html-export :"newman/myHTMLreport.html"'
//             }
            
//             steps {
//                 bat 'newman run AdminService/RegressionTest.postman_collection.json -e AdminService/env/DevApi.postman_environment.json --reporters cli,junit,htmlextra --reporter-junit-export "newman_result.xml" --reporter-htmlextra-export "newman_result.html"'
//             }
        }
        
//     	stage('DocStoreService Test') {
//             steps {
//                 bat 'newman run DocStoreService/RegressionTest.postman_collection.json -e DocStoreService/env/DevApi.postman_environment.json --disable-unicode'
//             }
//         }
    }
}
