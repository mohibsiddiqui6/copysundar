pipeline {
    agent {label 'slavenew'}
    stages {
        stage('Build') { 
             steps {
                sh 'mvn clean package'
        }
        }
       
         stage('push to jfrog') { 
             steps {
                rtUpload (
                serverId: 'jfrog',
                spec: '''{
                    "files": [
                {
                "pattern": "target/*.war",
                "target": "java-app/"
                }
         ]
    }''',
                )
                }
        }
        }
        
    }
