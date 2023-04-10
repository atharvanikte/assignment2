pipeline {
  agent any

  environment {
    NODE_VERSION = "14.16.1"
    APP_PORT = "3000"
  }

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/atharvanikte/assignment2.git'
      }
    }

    stage('Install Dependencies') {
      steps {
        sh "npm install"
      }
    }

    stage('Build') {
      steps {
        sh "npm run build"
      }
    }

    stage('Deploy') {
      steps {
        sh "npm start &"
        sh "sleep 10" // Wait for the server to start
        script {
          def appUrl = "http://localhost:${8080}"
        }
      }
    }
  }
}
