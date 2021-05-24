pipeline {

  agent {
              docker { 
                  image 'python:3.9.4'
                  registryUrl 'https://index.docker.io/v1/'
              }
        }
  stages {
    stage('Run Python') {
          steps {
                sh 'pip --version'
            }
    }
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
