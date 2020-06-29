pipeline {
  agent { docker { image 'python:3.7.2-alpine' } }
  //  agent python
  stages {
    stage('build') {
      steps {
        sh 'sudo adduser -D worker'
        sh 'cd /home/worker'
        sh 'sudo chown -R worker:worker /home/worker'
        sh 'pip install --user -r requirements.txt'
      //  sh 'pip install -r requirements.txt'
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
