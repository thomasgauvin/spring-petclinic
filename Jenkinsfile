pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh './mvnw package'
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
      steps {
        sh 'mvn deploy'
      }
    }

  }
}