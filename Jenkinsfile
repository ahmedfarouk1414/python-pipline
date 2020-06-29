pipeline {
  agent { docker { image 'python:3.7.2-alpine' } }
  //  agent python
  stages {
    stage('build') {
      steps {
            sh 'pip install -r requirements.txt --user root'
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
