pipeline {
  agent { 
    docker {
      args '-u 501:20' 
	  image 'python:3.7.2' 
    } 
  }
  stages {
    stage('build') {
      steps {
        sh 'pip install --verbose --user --build /Users/robrob/tmp/ -r requirements.txt'
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
