pipeline {
  agent {
         label 'slave'
        }

  
  
  stages {
    stage('build') {
      steps {
        sh 'pip3 install -r requirements.txt'
        sh 'pwd'
        sh 'ls -al' 
      }
    }
    stage('test') {
      steps {
        sh 'python3 test.py'
      }
      post {
        always {
          junit 'test-reports/*.xml'
        }
      }    
    }
  }
}        
        

