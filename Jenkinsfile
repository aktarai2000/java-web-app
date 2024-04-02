pipeline {
    agent any
    stages {
        stage('checkout code') {
            steps {
                git branch:'main', url:'https://github.com/aktarai2000/java-web-app.git'
            }
    
        }
        stage('build code') {
            steps {
                sh '/opt/maven/bin/mvn clean package'
            }

        }
        stage('deploy to tomcat') {
            steps {
                deploy adapters:[tomcat9(url: 'http://18.142.161.87:8080/' , credentialsId: 'tomcatcred')], war: '**/*.war'
            }  
              
        }
    }
}