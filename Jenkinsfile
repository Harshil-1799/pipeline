pipeline {
  agent any

  environment {
    DOCKERHUB_CREDENTIALS = credentials('docker')
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t myimage:latest .'
      }
    }
    stage('Login') {
      steps {
        sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-Harshil@123'
      }
    }
    stage('tag') {
      steps {
        sh 'docker tag myimage:latest shahharshil/myimage'
      }
    }
    stage('Push') {
      steps {
        sh 'docker push shahharshil/myimage'
      }
    }
  }
}
