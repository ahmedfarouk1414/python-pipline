pipeline {
  agent { docker { image 'python:3.7.2' } }
  //  agent python
  stages {
    stage('build') {
      steps {
        //sh 'pip install -r requirements.txt'
      //  sh python3 -m venv env
       // sh source ./env/bin/activate 
       // sh python -m pip install google-assistant-sdk[samples]
        //sh python -m pip install --user google-assistant-sdk[samples]
        sh 'sudo pip install -r requirements.txt'
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
