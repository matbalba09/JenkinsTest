pipeline {

    agent any
    
    stages {
       
        stage('Clean Workspace'){
            steps {
            cleanWs()
            }
        }
         
        stage('Checkout'){
            steps {
                checkout([$class: 'GitSCM',
                branches: [[name: '*/master']],
                doGenerateSubmoduleConfigurations: false,
                extensions: [],
                submoduleCfg: [],
                userRemoteConfigs: [[url: 'https://github.com/matbalba09/JenkinsTest.git']]])
            }
        }
        
    	stage('run Test newman') {
            steps {
                bat 'newman run PostmanTest//RegressionTest.postman_collection.json -e PostmanTest//env//DevApi.postman_environment.json --disable-unicode'
            }
        }
    }
}
