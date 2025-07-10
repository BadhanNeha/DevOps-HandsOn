pipeline {
  agent any

  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/BadhanNeha/DevOps-HandsOn.git'
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t neha2006/flask-demo:latest .'
      }
    }

    stage('Login & Push') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
          sh 'echo $PASSWORD | docker login -u $USERNAME --password-stdin'
          sh 'docker push yourdockerhubusername/flask-demo:latest'
        }
      }
    }
  }
}

