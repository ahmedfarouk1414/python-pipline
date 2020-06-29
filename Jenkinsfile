pipeline {
   agent 



pipeline {
  agent label: 'slave'
  
  stages {
    stage('build') {
      steps {
        sh 'pip install -r requirements.txt'
        sh pwd
        sh ls -al 
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
        

