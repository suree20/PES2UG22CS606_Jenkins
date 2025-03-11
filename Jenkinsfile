pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        build 'PES2UG22CS606-1'
        sh 'g++ new.cpp -o output' 
      }
    }
    stage('Test') {
      steps {
        sh './output'
        echo 'Test Stage Successful'
        post {
          always {
            junit 'target/surefire-reports/*.xml'
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deployment Successful'
      }
    }
  }
  post {
    failure {
      echo 'Pipeline failed.'
    }
  }
}
