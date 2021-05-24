pipeline {
  agent { docker { image 'python:3.9.4'
                   registryUrl "chiamakaobitube/node-jenkins"
                   registryCredentialsId "dockerhub" } }
  stages {
      stage('Test') {
        steps {
            sh 'pip --version'
        }
    }
    stage('build') {
      steps {
        sh 'pip install -r requirements.txt'
      }
    }
    stage('test') {
      steps {
        sh 'python test.py'
      }
      post {
        always {
          junit 'test-reports/*.xml'
        }
      }    
    }
  }
}
