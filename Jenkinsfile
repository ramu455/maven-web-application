node {
    def mavenHome = tool name: "maven3.9.0", type: 'maven'

    echo "The Node Name is: ${env.NODE_NAME}"

    echo "The Job Name is: ${env.JOB_NAME}"

    echo "The Build Number is: ${env.BUILD_NUMBER}"

   // properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '3'))
        stage('checkout code from github'){
            buildName "QA - ${env.BUILD_NUMBER}"
             buildDescription 'From Dev To QA'
        git credentialsId: '24504816-0753-4738-9361-fc75adba7447', url: 'https://github.com/ramu455/maven-web-application.git'
    }
       stage('Build with Maven'){
           sh "${mavenHome}/bin/mvn clean package"
       }
    /*
       stage('SonarQube'){
           sh "${mavenHome}/bin/mvn sonar:sonar"
       }
       stage('Nexus'){
            sh "${mavenHome}/bin/mvn deploy"
       }
       stage('Tomcat'){
           sshagent(['b702a0d3-b069-42b9-8c8d-0762fd35d39d']) {
            sh 'scp -o StrictHostKeyChecking=no target/maven-web-application.war ubuntu@172.31.11.226:/opt/tomcat/webapps'
}
           
          }
          */
}
