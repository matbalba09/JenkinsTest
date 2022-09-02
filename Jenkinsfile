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
        
//         stage('AdminService Test') {
//             steps {
//                 bat 'newman run AdminService/RegressionTest.postman_collection.json -e AdminService/env/DevApi.postman_environment.json -r htmlextra --reporter-htmlextra-export ./newman/adminService_report.html'
                
//                 publishHTML (target: [
//                     allowMissing: false, 
//                     alwaysLinkToLastBuild: true, 
//                     keepAll: false, 
//                     reportDir: 'C:\\Users\\Mat\\.jenkins\\workspace\\tman_Test_Github_Pipeline3_dev_2\\newman', 
//                     reportFiles: 'adminService_report.html', 
//                     reportName: 'adminService Newman HTML Report', 
//                     reportTitles: ''
//                 ])
//             }
//         }
        
//         stage('DocStoreService Test') {
//             steps {
// //                 bat 'newman run DocStoreService/RegressionTest.postman_collection.json -e DocStoreService/env/DevApi.postman_environment.json --disable-unicode -r htmlextra'
//                 bat 'newman run DocStoreService/RegressionTest.postman_collection.json -e DocStoreService/env/DevApi.postman_environment.json -r htmlextra --reporter-htmlextra-export ./newman/docStoreService_report.html'

//                 publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'C:\\Users\\Mat\\.jenkins\\workspace\\tman_Test_Github_Pipeline3_dev_2\\newman', reportFiles: 'report.html', reportName: 'Newman HTML Report', reportTitles: ''])
//             }
//         }
        
        stage('AdminService Test') {
            steps {
                bat 'newman run AdminService/AdminServiceTest.postman_collection.json -e AdminService/env/DevApi.postman_environment.json -r htmlextra --reporter-htmlextra-export ./newman/report.html'
                
                publishHTML (target: [
                    allowMissing: false, 
                    alwaysLinkToLastBuild: true, 
                    keepAll: false, 
                    reportDir: 'C:\\Users\\Mat\\.jenkins\\workspace\\tman_Test_Github_Pipeline3_dev_2\\newman', 
                    reportFiles: 'report.html', 
                    reportName: 'Newman HTML Report', 
                    reportTitles: ''
                ])
            }
        }
        
//     	stage('DocStoreService Test') {
//             steps {
//                 bat 'newman run DocStoreService/RegressionTest.postman_collection.json -e DocStoreService/env/DevApi.postman_environment.json --disable-unicode'
//             }
//         }
    }
}
