pipeline {
  agent any
  
  triggers {
    pollSCM('* * * * *')
  }

  stages {
    stage('Checkout') {
      steps {  
        git branch: 'main',
            url: '<URL>'
      }
    }
    stage('Build') {
      steps {
        sh '<COMMAND>'
      }  
    }
    stage('Test') {
      steps {
        sh '<COMMAND>'
      }
    }
    stage('Deploy') {
      steps {
        deploy adapters: [tomcat9(credentialsId: 'admin', url: 'https://github.com/Shinsped/mywebapp')], contextPath: null, war: 'path/to/war'
      }
    }
  }
}