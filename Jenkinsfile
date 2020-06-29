pipeline {
  agent { docker { image 'python:3' } }
  //  agent python
  stages {
    stage('build') {
      steps {
        sh 'sudo -H pip install -r requirements.txt'
      // sh python -m pip install google-assistant-sdk[samples]
        //sh python -m pip install --user google-assistant-sdk[samples]
        //sh 'pip install --no-cache-dir -r requirements.txt'
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
