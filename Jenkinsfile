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

        stage('Example') {
            steps {
                script {
                    def branchName = env.BRANCH_NAME
                    def variableValue
                    
                    // Set variable value based on branch
                    if (branchName == 'dev') {
                        variableValue = 'DocStoreService/env/DevApi.postman_environment.json'
                    } else if (branchName == 'staging') {
                        variableValue = 'DocStoreService/env/StgApi.postman_environment.json'
                    } else if (branchName == 'main') {
                        variableValue = 'main-value'
                    } else {
                        error("Invalid branch: $branchName")
                    }
                    
                    // Set environment variable
                    env.MY_VARIABLE = variableValue
                    // Use the variable in your build steps
                    echo "Branch: $branchName"
                    echo "Variable value: $variableValue"
                }
                
                bat "newman run DocStoreService/NewmanTest.postman_collection.json -e %MY_VARIABLE% -r htmlextra --reporter-htmlextra-export ./newman/report.html"

                // publishHTML (target: [
                //     allowMissing: false, 
                //     alwaysLinkToLastBuild: true, 
                //     keepAll: false, 
                //     reportDir: 'C:\\Users\\Mat\\.jenkins\\workspace\\tman_Test_Github_Pipeline3_dev_2\\newman', 
                //     reportFiles: 'report.html', 
                //     reportName: 'Newman HTML Report', 
                //     reportTitles: ''
                // ])
                publishHTML (target: [
                    allowMissing: false, 
                    alwaysLinkToLastBuild: true, 
                    keepAll: false, 
                    reportDir: 'newman', // Use relative path to workspace directory
                    reportFiles: 'report.html', 
                    reportName: 'Newman HTML Report', 
                    reportTitles: ''
                ])
            }
        }
        
//         stage('DocStoreService Dev') {
//             when {
//                 branch 'dev'
//             }
//             steps {
// //                 bat 'newman run DocStoreService/RegressionTest.postman_collection.json -e DocStoreService/env/DevApi.postman_environment.json --disable-unicode -r htmlextra'
//                 bat 'newman run DocStoreService/NewmanTest.postman_collection.json -e DocStoreService/env/DevApi.postman_environment.json  -r htmlextra --reporter-htmlextra-export ./newman/report.html'

//                 publishHTML (target: [
//                     allowMissing: false, 
//                     alwaysLinkToLastBuild: true, 
//                     keepAll: false, 
//                     reportDir: 'C:\\Users\\Mat\\.jenkins\\workspace\\newmanTestDev\\newman', 
//                     reportFiles: 'report.html', 
//                     reportName: 'Newman HTML Report', 
//                     reportTitles: ''
//                 ])
//             }
//         }

//         stage('DocStoreService Staging') {
//             when {
//                 branch 'staging'
//             }
            
//             steps {
// //                 bat 'newman run DocStoreService/RegressionTest.postman_collection.json -e DocStoreService/env/DevApi.postman_environment.json --disable-unicode -r htmlextra'
//                 bat 'newman run DocStoreService/NewmanTest.postman_collection.json -e DocStoreService/env/StgApi.postman_environment.json -r htmlextra --reporter-htmlextra-export ./newman/report.html'

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
