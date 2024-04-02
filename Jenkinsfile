node {
    stage ('checkoutcode') {
        git branch: 'main',url:'https://github.com/aktarai2000/java-web-app.git'
    }
    stage ('buildcode') {
        sh '/opt/maven/bin/mvn clean package'
    }
    stage ('deploytotomcat') {
        deploy  adapters: [tomcat9(url:'http://18.143.193.120:8080/',credentialsId:'tomcatcred')],war:'**/*.war'
    }
}