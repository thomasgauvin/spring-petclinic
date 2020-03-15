pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh 'mvn clean compile'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }

    stage('Deploy') {
      when {
        branch 'master'
      }
      steps {
        sh 'mvn deploy'
      }
    }

  }
   post {  
     success {  
         mail bcc: '', body: "<b>Build STATUS</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL of build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "Build PASSED: spring-petclinic -> ${env.JOB_NAME}", to: "thomasgauvin.cu@gmail.com";  
     }  
     failure {  
         mail bcc: '', body: "<b>Build STATUS</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL of build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "Build FAILED: spring-petclinic -> ${env.JOB_NAME}", to: "thomasgauvin.cu@gmail.com";  
     }  
   }  
}
