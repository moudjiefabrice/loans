pipeline {
 agent any
 stages {
     stage('Build') {
       steps {
         sh "mvn clean package"
       }
     }
     stage('Deploy') {
            steps {
              deploy adapters: [tomcat9(credentialsId: '', path: '',
              url: 'http://ec2-52-86-9-189.compute-1.amazonaws.com:9093/')],
              contextPath: 'javaApiApp', war: '**/*.war'
            }
          }
   }
}