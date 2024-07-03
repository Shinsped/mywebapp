pipeline {
  agent any
  
  triggers {
    pollSCM('* * * * *')
  }

  stages {
    stage('Checkout') {
      steps {  
        git branch: 'main',
            url: 'https://github.com/Shinsped/mywebapp'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean package'
      }  
    }
    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }
    stage('Deploy') {
      steps {
        deploy adapters: [tomcat9(credentialsId: 'admin', url: 'https://github.com/Shinsped/mywebapp')], contextPath: null, war: 'path/to/war'
      }
    }
  }
}