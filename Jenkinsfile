pipeline {
  agent {
    //docker {
     // image 'python:3'
      label 'python' 
  }
  //  agent python
  stages {
    stage('build') {
      steps {
            //sh 'chmod 777 -R /usr/local/lib/python3.7'
            //sh 'pip  --no-cache-dir install -r requirements.txt --user'
        
            sh """
            ls -la 
            pwd
           # pip3 install -r requirements.txt
            
            
            """
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
