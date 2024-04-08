pipeline {
    agent {
        node {
            label 'jenkins-slave-label'
        }
    }
    stages {
        stage ('checkoutcode') {
            steps {
                git branch: 'main' , url: 'https://github.com/aktarai2000/java-web-app.git'
            }
        }
        stage ('buildcode') {
            steps {
                sh '/opt/maven/bin/mvn clean package'
            }
        }
    }
}