pipeline {

  agent {
          docker { 
              image 'python:3.9.4'
            }
}
  stages {
    stage('Run python') {
      steps {
          sh 'pip --version'
      }
  }
    stage('build') {
      steps {
        sh '''
            python -m venv .venv flask
            cd flask
            . .venv/flask/activate
            pip install -r requirements.txt
          '''
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
