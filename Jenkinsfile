pipeline {
  agent { docker { image 'python:3.7.2' } }
  //  agent python
  stages {
    stage('build') {
      steps {
        //sh 'pip install -r requirements.txt'
        sh 'pip3 install -r requirements.txt --user --no-cache'
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
