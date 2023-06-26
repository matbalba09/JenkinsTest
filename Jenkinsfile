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
        
        stage('DocStoreService Dev') {
            when {
                branch 'dev'
            }
            environment {
                MY_ENV = "DocStoreService/env/DevApi.postman_environment.json"
            }
            steps {
//                 bat 'newman run DocStoreService/RegressionTest.postman_collection.json -e DocStoreService/env/DevApi.postman_environment.json --disable-unicode -r htmlextra'
                bat 'newman run DocStoreService/NewmanTest.postman_collection.json -e MY_ENV  -r htmlextra --reporter-htmlextra-export ./newman/report.html'

                publishHTML (target: [
                    allowMissing: false, 
                    alwaysLinkToLastBuild: true, 
                    keepAll: false, 
                    reportDir: 'C:\\Users\\Mat\\.jenkins\\workspace\\newmanTestDev\\newman', 
                    reportFiles: 'report.html', 
                    reportName: 'Newman HTML Report', 
                    reportTitles: ''
                ])
            }
        }

        stage('DocStoreService Staging') {
            when {
                branch 'staging'
            }
            
            steps {
//                 bat 'newman run DocStoreService/RegressionTest.postman_collection.json -e DocStoreService/env/DevApi.postman_environment.json --disable-unicode -r htmlextra'
                bat 'newman run DocStoreService/NewmanTest.postman_collection.json -e DocStoreService/env/StgApi.postman_environment.json -r htmlextra --reporter-htmlextra-export ./newman/report.html'

                publishHTML (target: [
                    allowMissing: false, 
                    alwaysLinkToLastBuild: true, 
                    keepAll: false, 
                    reportDir: 'C:\\Users\\Mat\\.jenkins\\workspace\\newmanTestStg\\newman', 
                    reportFiles: 'report.html', 
                    reportName: 'Newman HTML Report', 
                    reportTitles: ''
                ])
            }
        }
        
        
//         stage('AdminService Test') {
//             steps {
//                 bat 'newman run AdminService/NewmanTest.postman_collection.json -e AdminService/env/DevApi.postman_environment.json --disable-unicode -r htmlextra'
//                 bat 'newman run AdminService/NewmanTest.postman_collection.json -e AdminService/env/DevApi.postman_environment.json -r htmlextra --reporter-htmlextra-export ./newman/report.html'
                
//                 publishHTML (target: [
//                     allowMissing: false, 
//                     alwaysLinkToLastBuild: true, 
//                     keepAll: false, 
//                     reportDir: 'C:\\Users\\Mat\\.jenkins\\workspace\\tman_Test_Github_Pipeline3_dev_2\\newman', 
//                     reportFiles: 'report.html', 
//                     reportName: 'Newman HTML Report', 
//                     reportTitles: ''
//                 ])
//             }
//         }

    }
}
